---
name: rag-quarkus
description: Use when working with the RAG-Quarkus project — Quarkus 3.37 + LangChain4j RAG system. Covers Java/Quarkus backend development, LangChain4j integration, embeddings, document ingestion, Groq API, REST endpoints, security filters, rate limiting, and CDI configuration. Also use when discussing or modifying RAG architecture, ingestion pipelines, retrieval augmentation, or Quarkus-specific patterns like @ConfigMapping and SmallRye Fault Tolerance.
---

# RAG-Quarkus Development Skill

Use this skill when working on the RAG-Quarkus project: a Retrieval-Augmented Generation system built with Quarkus 3.37 and LangChain4j.

## Project Overview

RAG system that answers natural language questions based on indexed documents (PDF, DOCX, TXT, MD). Uses Groq API (llama-3.3-70b-versatile) as LLM and AllMiniLmL6V2 for local embeddings (384 dimensions, ONNX, no network calls).

## Architecture

```
POST /chat (X-API-Key required)
  → ApiKeyFilter → ChatResource (@RateLimit 10/min)
    → RagAssistant.chat(question)
      → @RegisterAiService (LangChain4j build-time impl)
      → @SystemMessage: "Respond ONLY with document context"
      → RetrieverProducer (EmbeddingStoreContentRetriever)
        → AllMiniLmL6V2 (local embeddings)
        → InMemoryEmbeddingStore
        → maxResults=3, minScore=0.0
      → Groq API (llama-3.3-70b-versatile, temp=0.3)
    → ChatResponse { answer }
```

## Project Structure

```
src/main/java/com/bryan/
├── features/
│   ├── chat/
│   │   ├── ChatResource.java           # POST /chat, @RateLimit(10/min)
│   │   ├── RagAssistant.java           # @RegisterAiService interface
│   │   └── records/
│   │       ├── ChatRequest.java        # DTO: { question }
│   │       └── ChatResponse.java       # DTO: { answer }
│   ├── ingestion/
│   │   ├── DocumentIngestor.java       # @PostConstruct ingestion
│   │   ├── DocumentLoaderFactory.java  # Parser factory by extension
│   │   ├── IngestionConfig.java        # @ConfigMapping rag.ingestion.*
│   │   └── exceptions/
│   │       └── DocumentLoadException.java
│   └── retrieval/
│       ├── RetrieverProducer.java      # Supplier<RetrievalAugmentor>
│       └── RetrievalConfig.java        # @ConfigMapping rag.retrieval.*
└── shared/
    ├── embedings/
    │   └── EmbeddingStoreProducer.java  # CDI: Store + EmbeddingModel
    ├── exceptions/
    │   ├── ErrorResponse.java           # Record { success, message, status }
    │   └── GlobalExceptionHandlers.java # RateLimit(429) + generic(500)
    └── security/
        └── ApiKeyFilter.java           # X-API-Key filter on /chat
```

## Key Patterns

### API Key Security (ApiKeyFilter)
```java
@Provider @Priority(Priorities.AUTHENTICATION)
public class ApiKeyFilter implements ContainerRequestFilter {
    @ConfigProperty(name = "app.api-key") String apiKey;
    // Only intercepts /chat paths
    // Returns 401 on invalid key
}
```

### Rate Limiting (SmallRye)
```java
@RateLimit(value = 10, window = 1, windowUnit = ChronoUnit.MINUTES)
public ChatResponse chat(@Valid ChatRequest request) { ... }
```

### Config Mapping (SmallRye)
```java
@ConfigMapping(prefix = "rag.ingestion")
public interface IngestionConfig {
    String documentsPath();
    int chunkSize();
    int chunkOverlap();
}
```

### Document Ingestion Pipeline
1. Load files from configured directory
2. Parse by extension (PDF→PdfBox, DOCX→Poi, TXT/MD→Text)
3. Split with recursive splitter (300 chars, 30 overlap)
4. Generate embeddings locally (AllMiniLmL6V2)
5. Store in InMemoryEmbeddingStore

### AI Service Interface
```java
@RegisterAiService
@SystemMessage("Respond ONLY with context from provided documents")
public interface RagAssistant {
    @UserMessage("{{question}}")
    String chat(String question);
}
```

## Configuration Properties

```properties
# LLM
quarkus.langchain4j.openai.base-url=https://api.groq.com/openai/v1
quarkus.langchain4j.openai.api-key=${GROQ_API_KEY}
quarkus.langchain4j.openai.chat-model.model-name=llama-3.3-70b-versatile
quarkus.langchain4j.openai.chat-model.temperature=0.3

# Ingestion
rag.ingestion.documents-path=src/main/resources/documents
rag.ingestion.chunk-size=300
rag.ingestion.chunk-overlap=30

# Retrieval
rag.retrieval.max-results=3
rag.retrieval.min-score=0.0

# Security
app.api-key=${API_KEY}
```

## Dependencies

| Dependency | Purpose |
|---|---|
| `quarkus-rest-jackson` | JSON serialization |
| `quarkus-rest` | JAX-RS / RESTEasy Reactive |
| `quarkus-langchain4j-openai` | LLM integration (OpenAI-compatible) |
| `quarkus-hibernate-validator` | @NotNull, @NotBlank validation |
| `quarkus-smallrye-fault-tolerance` | @RateLimit |
| `langchain4j-embeddings-all-minilm-l6-v2` | Local embeddings (ONNX) |
| `langchain4j-document-parser-apache-poi` | DOCX parsing |
| `langchain4j-document-parser-apache-pdfbox` | PDF parsing |

## Development Commands

```bash
# Dev mode
./gradlew quarkusDev

# Build
./gradlew build

# Über-JAR
./gradlew build -Dquarkus.package.jar.type=uber-jar

# Native (GraalVM)
./gradlew build -Dquarkus.native.enabled=true
```

## Environment Variables

```
GROQ_API_KEY=your_groq_api_key
API_KEY=your_access_api_key
```

## Testing

```bash
curl -X POST http://localhost:8080/chat \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your_api_key" \
  -d '{"question": "What is MAAC?"}'
```

## Code Style Notes

- Use records for DTOs (ChatRequest, ChatResponse, ErrorResponse)
- Use @ConfigMapping for typed configuration (not @ConfigProperty for complex configs)
- CDI producers for shared beans (EmbeddingStore, EmbeddingModel)
- Global exception mappers via @Provider
- Document ingestion runs on @PostConstruct (automatic on startup)
- InMemoryEmbeddingStore loses data on restart (re-indexes automatically)

## Production Considerations

| Aspect | Current | Recommendation |
|---|---|---|
| Vector store | InMemory | PgVector, Chroma, or Milvus |
| Security | X-API-Key header | OAuth2/JWT |
| API Key | Env var | Vault or secrets manager |
| Logging | Enabled | Disable in prod |
