# Contrato de eventos - document-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion documental

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `document.documento.created.v1` | `document-service` | `monitoring-service`, `audit-service` | `documento_id`, `tipo`, `owner`, `occurred_at` | v1 |
| `document.version.created.v1` | `document-service` | `monitoring-service`, `audit-service` | `documento_id`, `version_id`, `occurred_at` | v1 |
| `document.plantilla.updated.v1` | `document-service` | `audit-service` | `plantilla_id`, `schema_version`, `occurred_at` | v1 |

## Eventos consumidos

| Evento | Producer | Uso |
|--------|----------|-----|
| `academic.oferta.published.v1` | `academic-management-service` | Crear documentos base de oferta cuando aplique |
| `actors.aprendiz.updated.v1` | `actors-service` | Actualizar referencias documentales |

## Versionado

Cambios incompatibles crean sufijo `.v2`.
