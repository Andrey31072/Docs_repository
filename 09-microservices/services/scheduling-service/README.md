# scheduling-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Planeacion academica

## Proposito

Gestionar horarios, sesiones de clase, franjas, asignaciones y conflictos.

## Dominio de negocio

Programacion horaria.

## Responsabilidades

- Administrar `horario`, `sesion_clase`, `franja`, `asignacion` y `conflicto`.
- Orquestar disponibilidad academica, actores y ambientes.
- Detectar y registrar conflictos de programacion.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `scheduling_db` | Persistencia canonica |
| API consumida | `academic-management-service` | Fichas, programas, RAP y ofertas |
| API consumida | `training-environment-service` | Disponibilidad y reservas |
| API consumida | `actors-service` | Instructores y aprendices |
| API consumida | `reference-data-service` | Estados, franjas y parametros |
| API consumida | `iam-service` | Autorizacion |

## Base de datos

`scheduling_db`

## Eventos publicados

- `scheduling.horario.created.v1`
- `scheduling.asignacion.created.v1`
- `scheduling.conflicto.detected.v1`
- `scheduling.sesion-clase.cancelled.v1`

## Eventos consumidos

- `academic.ficha.created.v1`
- `environment.disponibilidad.changed.v1`
- `actors.instructor.availability-changed.v1`

## APIs expuestas

- `/api/v1/horarios`
- `/api/v1/sesiones-clase`
- `/api/v1/franjas`
- `/api/v1/asignaciones`
- `/api/v1/conflictos`

## APIs consumidas

- `iam-service`
- `reference-data-service`
- `academic-management-service`
- `training-environment-service`
- `actors-service`

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
