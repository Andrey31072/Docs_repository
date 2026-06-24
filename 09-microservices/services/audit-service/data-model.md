# Modelo de datos - audit-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Auditoria / Cumplimiento

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `auditoria` | `audit-service` | Registro inmutable de evento auditable |

## Relaciones

- `auditoria` referencia servicio, entidad, accion, usuario, timestamp y correlation id.
- No hay relaciones transaccionales directas con bases de otros servicios.

## Reglas de negocio

- Append-only: cada evento auditable crea un nuevo registro.
- No se permiten updates ni deletes.
- Los registros deben conservar `event_id`, `producer`, `entity_type`, `entity_id`, `action`, `occurred_at` y `correlation_id`.

## Restricciones

- Prohibidas actualizaciones de registros existentes.
- Prohibida eliminacion desde flujos de aplicacion.
- Acceso de lectura limitado a roles autorizados.
