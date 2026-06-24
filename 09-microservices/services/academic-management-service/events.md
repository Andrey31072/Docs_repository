# Contrato de eventos - academic-management-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Kevin Culma | Equipo: Coordinacion academica

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `academic.programa.updated.v1` | `academic-management-service` | `scheduling-service`, `monitoring-service`, `audit-service` | `programa_id`, `estado`, `occurred_at` | v1 |
| `academic.ficha.created.v1` | `academic-management-service` | `scheduling-service`, `monitoring-service` | `ficha_id`, `programa_id`, `occurred_at` | v1 |
| `academic.oferta.published.v1` | `academic-management-service` | `scheduling-service`, `document-service` | `oferta_id`, `centro_formacion_id`, `occurred_at` | v1 |

## Esquema

Todo evento debe incluir `event_id`, `producer`, `schema_version`, `occurred_at` y `correlation_id`.

## Versionado

Cambios incompatibles crean sufijo `.v2`.
