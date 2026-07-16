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

1. Disk Cleaner

Optimización

1. Generador de Horarios

Soporte TI

Priorizar experiencia profesional antes que proyectos.

Nunca inventar funcionalidades que no estén descritas en este archivo.

Si el recruiter pregunta sobre un proyecto, responder únicamente utilizando la información documentada aquí.