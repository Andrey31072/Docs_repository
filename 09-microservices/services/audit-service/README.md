# audit-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Auditoria / Cumplimiento

## Proposito

Registrar eventos auditables de forma append-only, sin actualizaciones, para trazabilidad y cumplimiento.

## Dominio de negocio

Auditoria.

## Responsabilidades

- Administrar `auditoria`.
- Consumir eventos auditables de todos los servicios.
- Garantizar inmutabilidad logica de registros.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `audit_db` | Persistencia append-only |
| Eventos | Todos los servicios | Registro auditable |

## Base de datos

`audit_db`

## Eventos publicados

- `audit.auditoria.recorded.v1` cuando se requiera confirmacion de auditoria.

## Eventos consumidos

- Eventos auditables de todos los microservicios.

## APIs expuestas

- `/api/v1/auditorias` para consulta autorizada.

## APIs consumidas

- `iam-service` para autorizacion de consultas si aplica.

## Regla critica

`audit-service` es append-only: no se permiten actualizaciones ni eliminaciones logicas o fisicas de registros de auditoria desde flujos de negocio.

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
