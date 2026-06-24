# Contrato de eventos - training-environment-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de ambientes

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `environment.ambiente.updated.v1` | `training-environment-service` | `scheduling-service`, `monitoring-service` | `ambiente_id`, `estado`, `occurred_at` | v1 |
| `environment.reserva.created.v1` | `training-environment-service` | `scheduling-service`, `audit-service` | `reserva_id`, `ambiente_id`, `franja_id`, `occurred_at` | v1 |
| `environment.disponibilidad.changed.v1` | `training-environment-service` | `scheduling-service` | `ambiente_id`, `desde`, `hasta`, `estado`, `occurred_at` | v1 |

## Eventos consumidos

| Evento | Producer | Uso |
|--------|----------|-----|
| `scheduling.sesion-clase.cancelled.v1` | `scheduling-service` | Liberar reserva asociada cuando aplique |

## Versionado

Cambios incompatibles crean sufijo `.v2`.
