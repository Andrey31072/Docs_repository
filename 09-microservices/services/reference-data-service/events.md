# Contrato de eventos - reference-data-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gobierno de datos

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `reference.catalogo.updated.v1` | `reference-data-service` | Servicios con cache | `catalogo_id`, `codigo`, `occurred_at` | v1 |
| `reference.parametro.updated.v1` | `reference-data-service` | Servicios con parametros | `parametro_id`, `codigo`, `occurred_at` | v1 |
| `reference.centro-formacion.updated.v1` | `reference-data-service` | Academic, actors, scheduling | `centro_formacion_id`, `occurred_at` | v1 |

## Esquema

Todo evento debe incluir `event_id`, `producer`, `schema_version`, `occurred_at` y `correlation_id`.

## Versionado

Cambios incompatibles crean sufijo `.v2`.
