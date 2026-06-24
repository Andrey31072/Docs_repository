# Contrato de eventos - scheduling-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Planeacion academica

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `scheduling.horario.created.v1` | `scheduling-service` | `monitoring-service`, `audit-service` | `horario_id`, `centro_formacion_id`, `occurred_at` | v1 |
| `scheduling.asignacion.created.v1` | `scheduling-service` | `training-environment-service`, `actors-service`, `audit-service` | `asignacion_id`, `franja_id`, `occurred_at` | v1 |
| `scheduling.conflicto.detected.v1` | `scheduling-service` | `monitoring-service`, `audit-service` | `conflicto_id`, `tipo`, `severity`, `occurred_at` | v1 |
| `scheduling.sesion-clase.cancelled.v1` | `scheduling-service` | `training-environment-service`, `actors-service`, `audit-service` | `sesion_clase_id`, `reason`, `occurred_at` | v1 |

## Eventos consumidos

| Evento | Producer | Uso |
|--------|----------|-----|
| `academic.ficha.created.v1` | `academic-management-service` | Preparar programacion |
| `environment.disponibilidad.changed.v1` | `training-environment-service` | Recalcular conflictos |
| `actors.instructor.availability-changed.v1` | `actors-service` | Recalcular asignaciones |

## Versionado

Cambios incompatibles crean sufijo `.v2`.
