# Contrato de eventos - iam-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguridad / IAM

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `iam.usuario.created.v1` | `iam-service` | `audit-service`, `monitoring-service` | `event_id`, `usuario_id`, `occurred_at` | v1 |
| `iam.rol.assigned.v1` | `iam-service` | `audit-service` | `event_id`, `usuario_id`, `rol_id`, `occurred_at` | v1 |
| `iam.token.revoked.v1` | `iam-service` | `audit-service` | `event_id`, `token_id`, `reason`, `occurred_at` | v1 |

## Esquema

Todo evento debe incluir `event_id`, `producer`, `schema_version`, `occurred_at` y `correlation_id`.

## Versionado

Cambios incompatibles crean sufijo `.v2` y periodo de convivencia.
