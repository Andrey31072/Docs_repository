# Gobierno de microservicios

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Arquitectura / Desarrollo

## Contexto

Este documento estandariza naming, ownership, versionado, contratos, eventos y observabilidad para los microservicios del proyecto.

## Naming convention

| Elemento | Convencion | Ejemplo |
|----------|------------|---------|
| Servicio | `<bounded-context>-service` en kebab-case | `scheduling-service` |
| Base de datos | `<context>_db` en snake_case | `scheduling_db` |
| Evento | `<dominio>.<entidad>.<accion>.v<version>` | `scheduling.horario.created.v1` |
| API tag | Nombre del recurso plural | `horarios` |
| Ruta base | `/api/v<version>/<recurso>` | `/api/v1/horarios` |
| Correlation id | `x-correlation-id` | UUID generado por gateway o cliente |

## Ownership

Cada microservicio debe declarar:

| Campo | Descripcion |
|-------|-------------|
| Owner funcional | Area responsable del proceso de negocio |
| Owner tecnico | Equipo responsable de codigo, contratos y operacion |
| Data owner | Responsable de entidades y calidad de datos |
| Operador | Responsable de despliegue, monitoreo e incidentes |

## Versionado

| Artefacto | Regla |
|-----------|-------|
| API REST | Version mayor en URL: `/api/v1` |
| Eventos | Version en nombre y esquema: `.v1` |
| Base de datos | Migraciones versionadas y reversibles cuando aplique |
| Documentacion | Fecha, estado, changelog y enlaces cruzados |

Cambios breaking deben tener ADR o decision aprobada, estrategia de migracion y periodo de convivencia si hay consumidores activos.

## Contratos

| Tipo | Ubicacion | Regla |
|------|-----------|-------|
| API operativa | `09-microservices/services/<servicio>/api-contract.md` | Describe endpoints, request, response, errores y seguridad |
| OpenAPI formal | `07-api/contracts/openapi/` | Se crea cuando el contrato sea estable |
| Eventos | `09-microservices/services/<servicio>/events.md` | Incluye producer, consumers, payload, esquema y versionado |
| Datos | `09-microservices/services/<servicio>/data-model.md` | Define entidades propias, relaciones y restricciones |

## Eventos

Los eventos deben ser:

- Idempotentes para consumidores.
- Versionados.
- Compatibles hacia atras cuando sea posible.
- Trazables con `event_id`, `occurred_at`, `producer`, `schema_version` y `correlation_id`.
- Sin datos sensibles innecesarios.

## Observabilidad

Cada servicio debe documentar:

| Elemento | Minimo esperado |
|----------|-----------------|
| Logs | Nivel, campos obligatorios, correlation id, errores |
| Metricas | Latencia, tasa de error, throughput, saturacion |
| Trazas | Entrada API, llamadas a otros servicios y eventos |
| Alertas | Sintoma, umbral, severidad y accion |
| Dashboards | Disponibilidad, rendimiento, errores y negocio |

## Criterios de actualizacion

Actualizar este documento cuando cambien convenciones de naming, versionado, contratos, eventos, observabilidad o politicas de ownership.

## Trazabilidad

- [Documentacion de microservicios](./microservices-documentation.md)
- [Catalogo de servicios](../09-microservices/service-catalog.md)
- [Matriz de dependencias](../09-microservices/service-dependency-matrix.md)
- [Disponibilidad y escalabilidad](../09-microservices/availability-scalability.md)
