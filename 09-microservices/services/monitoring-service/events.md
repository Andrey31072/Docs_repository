# Contrato de eventos - monitoring-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguimiento institucional

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `monitoring.alerta.created.v1` | `monitoring-service` | `audit-service`, servicios afectados | `alerta_id`, `severity`, `source`, `occurred_at` | v1 |
| `monitoring.notificacion.sent.v1` | `monitoring-service` | `audit-service` | `notificacion_id`, `channel`, `status`, `occurred_at` | v1 |
| `monitoring.plan-mejoramiento.created.v1` | `monitoring-service` | `audit-service` | `plan_mejoramiento_id`, `owner`, `occurred_at` | v1 |

## Eventos consumidos

| Evento | Producer | Uso |
|--------|----------|-----|
| `scheduling.conflicto.detected.v1` | `scheduling-service` | Generar KPI o alerta |
| `academic.ficha.created.v1` | `academic-management-service` | Actualizar indicadores academicos |
| `actors.bitacora.created.v1` | `actors-service` | Seguimiento |
| `document.version.created.v1` | `document-service` | Seguimiento documental |

## Versionado

Cambios incompatibles crean sufijo `.v2`.
