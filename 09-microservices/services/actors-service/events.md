# Contrato de eventos - actors-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de actores

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `actors.instructor.availability-changed.v1` | `actors-service` | `scheduling-service`, `monitoring-service` | `instructor_id`, `desde`, `hasta`, `estado`, `occurred_at` | v1 |
| `actors.aprendiz.updated.v1` | `actors-service` | `monitoring-service`, `document-service` | `aprendiz_id`, `estado`, `occurred_at` | v1 |
| `actors.bitacora.created.v1` | `actors-service` | `monitoring-service`, `audit-service` | `bitacora_id`, `aprendiz_id`, `occurred_at` | v1 |

## Eventos consumidos

| Evento | Producer | Uso |
|--------|----------|-----|
| `scheduling.asignacion.created.v1` | `scheduling-service` | Registrar participacion en programacion |
| `scheduling.sesion-clase.cancelled.v1` | `scheduling-service` | Ajustar disponibilidad cuando aplique |

## Versionado

Cambios incompatibles crean sufijo `.v2`.
