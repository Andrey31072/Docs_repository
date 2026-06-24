# actors-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de actores

## Proposito

Gestionar actores academicos y productivos relacionados con la formacion.

## Dominio de negocio

Actores.

## Responsabilidades

- Administrar `instructor`, `aprendiz`, `empresa`, `etapa_productiva` y `bitacora`.
- Proveer informacion de disponibilidad y asignacion de actores.
- Proteger datos personales.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `actors_db` | Persistencia canonica |
| API consumida | `reference-data-service` | Estados, catalogos y centros |
| API consumida | `iam-service` | Identidad y permisos |

## Base de datos

`actors_db`

## Eventos publicados

- `actors.instructor.availability-changed.v1`
- `actors.aprendiz.updated.v1`
- `actors.bitacora.created.v1`

## Eventos consumidos

- `scheduling.asignacion.created.v1`
- `scheduling.sesion-clase.cancelled.v1`

## APIs expuestas

- `/api/v1/instructores`
- `/api/v1/aprendices`
- `/api/v1/empresas`
- `/api/v1/etapas-productivas`
- `/api/v1/bitacoras`

## APIs consumidas

- `iam-service`
- `reference-data-service`

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
