# document-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion documental

## Proposito

Gestionar documentos, versiones y plantillas del ecosistema.

## Dominio de negocio

Documentos.

## Responsabilidades

- Administrar `documento`, `version` y `plantilla`.
- Mantener versionado documental y trazabilidad.
- Asociar documentos a dominios academicos o actores cuando aplique.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `document_db` | Persistencia canonica |
| API consumida | `iam-service` | Permisos |
| API consumida | `academic-management-service` | Asociaciones academicas |
| API consumida | `actors-service` | Asociaciones con actores |

## Base de datos

`document_db`

## Eventos publicados

- `document.documento.created.v1`
- `document.version.created.v1`
- `document.plantilla.updated.v1`

## Eventos consumidos

- `academic.oferta.published.v1`
- `actors.aprendiz.updated.v1`

## APIs expuestas

- `/api/v1/documentos`
- `/api/v1/documentos/{id}/versiones`
- `/api/v1/plantillas`

## APIs consumidas

- `iam-service`
- `academic-management-service`
- `actors-service`

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
