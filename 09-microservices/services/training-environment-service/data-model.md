# Modelo de datos - training-environment-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de ambientes

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `ambiente` | `training-environment-service` | Espacio de formacion |
| `inventario` | `training-environment-service` | Recursos del ambiente |
| `mantenimiento` | `training-environment-service` | Intervencion planificada o correctiva |
| `reserva` | `training-environment-service` | Bloqueo de uso de ambiente |
| `disponibilidad` | `training-environment-service` | Capacidad temporal disponible |

## Relaciones

- Un `ambiente` tiene `inventario`.
- Un `ambiente` puede tener varios `mantenimiento`.
- Una `reserva` ocupa disponibilidad de un `ambiente`.

## Reglas de negocio

- No puede existir doble reserva para la misma franja y ambiente.
- Mantenimiento bloquea disponibilidad.
- Las reservas deben ser idempotentes.

## Restricciones

- El servicio es owner unico de disponibilidad de ambientes.
- Estados y tipos se referencian desde `reference-data-service`.
