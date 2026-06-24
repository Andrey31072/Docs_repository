# Contrato de eventos - audit-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Auditoria / Cumplimiento

## Eventos consumidos

| Evento | Producer | Uso |
|--------|----------|-----|
| `iam.*.v1` | `iam-service` | Auditar cambios de identidad y acceso |
| `reference.*.v1` | `reference-data-service` | Auditar cambios de catalogos |
| `academic.*.v1` | `academic-management-service` | Auditar cambios academicos |
| `environment.*.v1` | `training-environment-service` | Auditar reservas y disponibilidad |
| `scheduling.*.v1` | `scheduling-service` | Auditar horarios, asignaciones y conflictos |
| `actors.*.v1` | `actors-service` | Auditar cambios de actores y bitacoras |
| `document.*.v1` | `document-service` | Auditar documentos y versiones |
| `monitoring.*.v1` | `monitoring-service` | Auditar alertas y planes |

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `audit.auditoria.recorded.v1` | `audit-service` | Observabilidad / cumplimiento | `auditoria_id`, `source_event_id`, `occurred_at` | v1 |

## Esquema

Cada evento consumido debe transformarse a un registro append-only con trazabilidad al evento original.

## Versionado

Cambios incompatibles crean sufijo `.v2` y no alteran registros historicos.
