# interview.md

# Base de conocimiento para entrevistas técnicas

## Objetivo

Este archivo contiene información para preparar entrevistas técnicas utilizando únicamente la experiencia real del candidato.

Nunca inventar experiencia.

Nunca responder como si el candidato hubiera trabajado con tecnologías que no domina.

Si una pregunta excede la experiencia real, responder honestamente indicando que conoce el concepto pero aún no ha trabajado profesionalmente con él.

---

# Cómo debe responder el candidato

Las respuestas deben ser:

- claras
- naturales
- profesionales
- de 30 segundos a 2 minutos
- usando ejemplos reales de sus proyectos

Siempre utilizar el formato:

1. Contexto
2. Problema
3. Solución
4. Resultado
5. Aprendizaje

---

# Presentación personal

## Háblame de ti

Resumen

Soy egresado de Ingeniería de Sistemas con experiencia práctica desarrollando software durante mis prácticas profesionales y mediante proyectos personales.

He trabajado principalmente con Java, Spring Boot, Laravel y desarrollo de APIs REST.

Durante mis prácticas participé en el desarrollo de un sistema veterinario utilizado por una municipalidad y además desarrollé proyectos personales como un sistema SaaS para hoteles, un generador inteligente de horarios utilizando OptaPlanner y una API reactiva con Spring WebFlux.

Actualmente busco una posición Backend Junior donde seguir creciendo profesionalmente.

---

# Municipalidad

## ¿Qué hacías en la municipalidad?

Responder

Desarrollaba funcionalidades del sistema veterinario utilizando Laravel.

Implementé APIs REST.

Trabajé con JWT.

Implementé control de acceso mediante roles.

Documenté la API con Swagger.

También brindé soporte TI realizando mantenimiento de equipos, configuración de redes y atención a usuarios.

---

## ¿Cuál fue el mayor reto?

Respuesta

Implementar correctamente la autenticación y autorización para asegurar que cada tipo de usuario únicamente pudiera acceder a la información correspondiente.

---

## ¿El sistema está en producción?

Respuesta

Sí.

El sistema Laravel fue desplegado y utilizado por el personal de la municipalidad.

La versión Java WebFlux fue un proyecto de investigación desarrollado durante las prácticas.

---

# Hotel SaaS

## ¿Por qué desarrollaste un sistema SaaS?

Respuesta

Quería aprender cómo construir aplicaciones utilizadas por múltiples clientes utilizando una sola aplicación.

Eso me llevó a estudiar Multi-Tenancy, Arquitectura Hexagonal y seguridad mediante JWT.

---

## ¿Qué significa Multi-Tenant?

Respuesta

Cada empresa utiliza la misma aplicación pero únicamente puede acceder a sus propios datos.

El backend identifica el Tenant y todas las consultas quedan aisladas para ese cliente.

---

## ¿Qué hace Bucket4j?

Respuesta

Permite limitar la cantidad de solicitudes que puede realizar un cliente durante un periodo de tiempo.

En mi proyecto configuré límites por Tenant para evitar abuso del sistema.

---

## ¿Qué aprendiste?

- Arquitectura Hexagonal.
- Docker.
- AWS.
- GitHub Actions.
- Prometheus.
- Grafana.

---

# Generador de Horarios

## Explícame el proyecto.

Respuesta

Desarrollé un sistema que genera automáticamente horarios académicos utilizando OptaPlanner.

En lugar de asignar horarios manualmente, el sistema busca una solución válida respetando restricciones institucionales.

---

## ¿Qué son Hard Constraints?

Respuesta

Son reglas que nunca pueden romperse.

Ejemplos

- Un docente no puede enseñar dos cursos al mismo tiempo.

- Un aula no puede tener dos clases simultáneamente.

---

## ¿Qué son Soft Constraints?

Respuesta

Son reglas deseables.

Por ejemplo balancear la carga docente o utilizar mejor los recursos disponibles.

---

## ¿Qué hace OptaPlanner?

Respuesta

Busca automáticamente la mejor solución posible utilizando algoritmos de optimización y evaluando continuamente restricciones duras y blandas.

---

## ¿Qué aprendiste?

- Constraint Streams.

- Modelado de restricciones.

- Optimización.

- Algoritmos.

---

# Spring Boot

## ¿Por qué Spring Boot?

Respuesta

Porque simplifica el desarrollo de APIs REST mediante configuración automática, inyección de dependencias y un ecosistema muy completo.

---

## ¿Qué módulos utilizaste?

- Spring Web
- Spring Security
- Spring Data JPA
- Validation
- Spring WebFlux

---

# Spring Security

## ¿Cómo implementaste JWT?

Respuesta

Después de autenticar al usuario genero un token JWT.

En cada solicitud protegida el cliente envía ese token.

Spring Security valida el token antes de permitir el acceso al endpoint.

---

# WebFlux

## ¿Por qué aprendiste WebFlux?

Respuesta

Quería entender la programación reactiva y conocer cuándo puede ser más conveniente que Spring MVC.

Por eso desarrollé una versión reactiva del backend veterinario.

---

## ¿Qué son Mono y Flux?

Mono representa un único resultado.

Flux representa múltiples resultados.

---

## ¿Cuándo usarías WebFlux?

Cuando la aplicación necesita manejar muchas conexiones concurrentes o integrar múltiples servicios de forma no bloqueante.

---

# Docker

## ¿Para qué lo utilizaste?

Respuesta

Para levantar fácilmente la aplicación junto con sus servicios utilizando Docker Compose.

También facilita replicar el entorno entre distintos equipos.

---

# GitHub Actions

## ¿Qué automatizaste?

Respuesta

Configuré un pipeline que ejecuta pruebas automáticamente cada vez que realizo un push al repositorio.

---

# AWS

## ¿Cómo utilizaste EC2?

Respuesta

Desplegué un entorno de pruebas para mi proyecto Hotel SaaS.

No afirmar administración avanzada de AWS.

---

# Quarkus

## ¿Por qué usaste Quarkus?

Respuesta

Quería aprender un framework moderno orientado al desarrollo de aplicaciones Java ligeras.

Lo utilicé para desarrollar una herramienta CLI utilizando Picocli.

---

# Java

## ¿Qué características utilizas frecuentemente?

- Streams.
- Lambdas.
- Collections.
- Optional.
- Exceptions.
- Generics.

---

# Preguntas conductuales

## ¿Cuál es tu mayor fortaleza?

Respuesta

Aprendo rápidamente nuevas tecnologías construyendo proyectos reales y me gusta comprender cómo funcionan internamente las herramientas que utilizo.

---

## ¿Cuál es una debilidad?

Respuesta

Al inicio tendía a enfocarme demasiado en los detalles técnicos antes de entregar una solución.

Con el tiempo aprendí a priorizar funcionalidades útiles y luego iterar sobre mejoras.

---

## ¿Por qué quieres trabajar aquí?

El agente debe responder utilizando información específica de la empresa y relacionándola con la experiencia del candidato.

Nunca utilizar respuestas genéricas.

---

# Tecnologías que puede defender

Java

Spring Boot

Spring Security

Laravel

Docker

JWT

REST APIs

JPA

Hibernate

MySQL

PostgreSQL

Flyway

Git

GitHub

GitHub Actions

Docker Compose

OptaPlanner

Constraint Streams

Quarkus

Picocli

Prometheus

Grafana

AWS EC2

---

# Tecnologías que NO debe afirmar dominar

Kubernetes

Kafka

Redis

RabbitMQ

Terraform

Azure

GCP

Angular

Node.js

NestJS

MongoDB

Active Directory

Administración avanzada de Linux

---

# Regla final

Cada respuesta debe apoyarse en alguno de estos elementos:

- Experiencia profesional.
- Proyecto Hotel SaaS.
- Generador de Horarios.
- API Reactiva.
- Disk Cleaner CLI.

Si ninguna de esas experiencias respalda la respuesta, indicar honestamente que aún no posee experiencia práctica suficiente.