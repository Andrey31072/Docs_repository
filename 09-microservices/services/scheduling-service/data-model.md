# Modelo de datos - scheduling-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Planeacion academica

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `horario` | `scheduling-service` | Plan de programacion |
| `sesion_clase` | `scheduling-service` | Sesion programada |
| `franja` | `scheduling-service` | Bloque temporal |
| `asignacion` | `scheduling-service` | Relacion entre ficha, instructor, ambiente y franja |
| `conflicto` | `scheduling-service` | Incumplimiento o choque detectado |

## Relaciones

- Un `horario` contiene varias `sesion_clase`.
- Una `sesion_clase` se ubica en una `franja`.
- Una `asignacion` vincula referencias externas de instructor, ficha y ambiente.
- Un `conflicto` se asocia a horario, sesion o asignacion.

## Reglas de negocio

- No se puede asignar el mismo instructor a dos sesiones simultaneas.
- No se puede reservar el mismo ambiente para dos sesiones simultaneas.
- Todo conflicto debe quedar trazado y, si aplica, auditado.

## Restricciones

- Guardar solo IDs externos de ficha, instructor y ambiente.
- Usar operaciones idempotentes para asignaciones y reservas.
