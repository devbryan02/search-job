# Proyectos

Este archivo es la fuente oficial de información sobre los proyectos del candidato.

Toda descripción de proyectos, CV, entrevista, carta de presentación o perfil profesional debe basarse únicamente en esta información.

Nunca inventar funcionalidades, tecnologías o resultados.

---

# Proyecto

## Hotel SaaS Multi-Tenant (Zowy)

Repositorio

https://github.com/devbryan02/hotel-saas-back

Estado

Proyecto personal en desarrollo.

Objetivo

Construir un backend SaaS para la administración de hoteles donde múltiples empresas (tenants) compartan la misma aplicación sin compartir sus datos.

Rol

Desarrollador Backend.

Stack

- Java 21
- Spring Boot
- Spring Security
- Spring Data JPA
- PostgreSQL
- Flyway
- Docker
- Docker Compose
- Bucket4j
- GitHub Actions
- AWS EC2
- Prometheus
- Grafana

Arquitectura

- Arquitectura Hexagonal
- Clean Code
- SOLID
- Multi-Tenancy

Características principales

- API REST
- Autenticación JWT
- Roles
- Rate Limiting por Tenant
- Migraciones con Flyway
- Docker Compose
- Monitoreo
- CI/CD básico
- Tests unitarios

Logros

- Implementación de autenticación JWT.
- Gestión aislada por Tenant.
- Configuración de Bucket4j limitando solicitudes por Tenant.
- Automatización de pruebas mediante GitHub Actions.
- Despliegue de pruebas en AWS EC2.
- Configuración de Prometheus y Grafana para monitoreo.

Tecnologías destacables

Spring Boot

Spring Security

Bucket4j

Docker

AWS

PostgreSQL

Flyway

Prometheus

Grafana

Palabras clave ATS

Java

Spring Boot

REST API

Docker

AWS

JWT

PostgreSQL

Microservices (solo mencionar arquitectura relacionada, nunca afirmar experiencia real en microservicios si no aplica)

---

# Proyecto

## Generador Inteligente de Horarios Académicos

Repositorio

https://github.com/devbryan02/Generador-de-horarios

Estado

Proyecto académico avanzado.

Objetivo

Automatizar la generación de horarios académicos respetando restricciones institucionales mediante algoritmos de optimización.

Rol

Desarrollador Backend.

Stack

- Java 17
- Spring Boot 3
- Spring Data JPA
- SQL Server
- OptaPlanner 9.44

Arquitectura

- Clean Architecture

Problema resuelto

La asignación manual de horarios produce conflictos entre docentes, aulas y disponibilidad.

El sistema genera automáticamente horarios válidos.

Restricciones duras

- Choques de docentes.
- Choques de aulas.
- Compatibilidad aula-curso.
- Disponibilidad docente.

Restricciones blandas

- Balance de carga docente.
- Mejor utilización de recursos.

Características

- Constraint Streams.
- Solver.
- Construction Heuristic.
- Local Search.
- API REST.
- Consulta por periodo académico.
- Evaluación Hard Score.
- Evaluación Soft Score.

Aprendizajes

- Optimización combinatoria.
- Modelado de restricciones.
- Constraint Streams.
- Diseño de algoritmos.
- Clean Architecture.

Palabras ATS

OptaPlanner

Constraint Streams

Optimization

Scheduling

Spring Boot

Java

SQL Server

REST API

---

# Proyecto

## API Reactiva Veterinaria

Repositorio

https://github.com/devbryan02/veterinaria-app-backend

Estado

Proyecto desarrollado durante las prácticas.

Objetivo

Reimplementar el backend del sistema veterinario utilizando programación reactiva con Java.

Rol

Backend Developer.

Stack

- Java
- Spring Boot
- Spring WebFlux
- Reactor

Objetivo técnico

Aprender programación reactiva reemplazando el backend Laravel por una solución no bloqueante.

Características

- Mono
- Flux
- REST API
- Programación reactiva
- Arquitectura por capas

Aprendizajes

- Programación reactiva.
- Reactor.
- Flujo no bloqueante.
- Diseño de APIs reactivas.

Palabras ATS

Spring WebFlux

Reactive Programming

Reactor

REST API

Java

---

# Proyecto

## Disk Cleaner CLI

Repositorio

https://github.com/devbryan02/disk-cleaner-quarkus-cli

Estado

Proyecto personal.

Objetivo

Crear una herramienta de línea de comandos para automatizar tareas de mantenimiento en Windows.

Rol

Desarrollador Backend.

Stack

- Java 25
- Quarkus
- Picocli
- Java NIO

Características

- Limpieza de temporales.
- Organización automática de Downloads.
- Limpieza de Papelera.
- Búsqueda de archivos grandes.
- Modo Dry Run.

Aprendizajes

- Desarrollo CLI.
- Manipulación del sistema de archivos.
- Java NIO.
- Picocli.

Palabras ATS

Quarkus

CLI

Picocli

Java

Java NIO

---

# Proyecto

## RAG-Quarkus (Retrieval-Augmented Generation)

Repositorio

https://github.com/devbryan02/rag-quarkus

Estado

Proyecto personal en desarrollo.

Objetivo

Construir un sistema RAG (Retrieval-Augmented Generation) que permita realizar preguntas en lenguaje natural sobre documentos indexados (PDF, DOCX, TXT, MD) y obtenga respuestas basadas exclusivamente en el contenido de esos documentos.

Rol

Desarrollador Backend.

Stack

- Java 21
- Quarkus 3.37
- LangChain4j
- Groq API (compatible OpenAI)
- AllMiniLmL6V2 (embeddings locales)
- SmallRye Fault Tolerance
- Hibernate Validator
- RESTEasy Reactive

Arquitectura

- API REST
- RAG (Retrieval-Augmented Generation)
- Embeddings locales (ONNX, 384 dimensiones)
- InMemory Embedding Store
- Rate Limiting
- API Key Authentication

Características principales

- POST /chat con validación de API Key
- Rate Limiting (10 req/min por cliente)
- Ingesta automática de documentos al arrancar
- Parsing de PDF, DOCX, TXT, MD
- Splitting recursivo (300 chars, overlap 30)
- Embeddings locales sin llamadas a red
- LLM via Groq API (llama-3.3-70b-versatile)
- System message restringiendo respuestas al contexto de documentos
- Manejo global de errores (429, 500)
- Configuración tipada con @ConfigMapping

Pipeline

1. Carga de documentos por extensión
2. Splitting recursivo en chunks
3. Generación de embeddings locales
4. Almacenamiento en InMemoryEmbeddingStore
5. Pregunta del usuario
6. Retrieval de contexto relevante
7. Generación de respuesta via LLM

Aprendizajes

- Retrieval-Augmented Generation.
- LangChain4j con Quarkus.
- Embeddings y similitud semántica.
- Integración con APIs de LLM.
- SmallRye Fault Tolerance.
- Seguridad con API Key.
- Configuración tipada en Quarkus.

Palabras ATS

RAG

Retrieval-Augmented Generation

Quarkus

LangChain4j

Embeddings

LLM

API REST

Java

Groq

ONNX

---

# Reglas para el agente

Nunca mostrar más de tres proyectos en el CV.

Prioridad por tipo de vacante

Java Backend

1. Hotel SaaS
2. Generador de Horarios
3. API Reactiva

Spring Boot

1. Hotel SaaS
2. API Reactiva
3. Generador

Laravel

1. Municipalidad
2. API Reactiva

Quarkus

1. RAG-Quarkus
2. Disk Cleaner

RAG / IA / LLM

1. RAG-Quarkus
2. Hotel SaaS (como backend robusto)

Optimización

1. Generador de Horarios

Soporte TI

Priorizar experiencia profesional antes que proyectos.

Nunca inventar funcionalidades que no estén descritas en este archivo.

Si el recruiter pregunta sobre un proyecto, responder únicamente utilizando la información documentada aquí.