# training-environment-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de ambientes

## Proposito

Gestionar ambientes de formacion, inventario, mantenimiento, reservas y disponibilidad.

## Dominio de negocio

Ambientes de formacion.

## Responsabilidades

- Administrar `ambiente`, `inventario`, `mantenimiento`, `reserva` y `disponibilidad`.
- Proveer disponibilidad de ambientes a programacion.
- Evitar reservas duplicadas.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `env_db` | Persistencia canonica |
| API consumida | `reference-data-service` | Estados, tipos y centros |

## Base de datos

`env_db`

## Eventos publicados

- `environment.ambiente.updated.v1`
- `environment.reserva.created.v1`
- `environment.disponibilidad.changed.v1`

## Eventos consumidos

- `scheduling.sesion-clase.cancelled.v1` para liberar reservas cuando aplique.

## APIs expuestas

- `/api/v1/ambientes`
- `/api/v1/disponibilidades`
- `/api/v1/reservas`
- `/api/v1/mantenimientos`

## APIs consumidas

- `reference-data-service`

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
