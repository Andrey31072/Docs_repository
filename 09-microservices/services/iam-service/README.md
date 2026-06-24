# iam-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguridad / IAM

## Proposito

Gestionar identidad, autenticacion, autorizacion, sesiones y tokens del ecosistema.

## Dominio de negocio

Identidad y acceso.

## Responsabilidades

- Administrar `usuario`, `rol`, `permiso`, `sesion` y `token`.
- Emitir, validar y revocar tokens.
- Exponer permisos para otros servicios.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `iam_db` | Persistencia canonica |
| Consumidores | Todos los servicios | Validacion de identidad y permisos |

## Base de datos

`iam_db`

## Eventos publicados

- `iam.usuario.created.v1`
- `iam.rol.assigned.v1`
- `iam.token.revoked.v1`

## Eventos consumidos

- Ninguno obligatorio en la version inicial.

## APIs expuestas

- `/api/v1/auth`
- `/api/v1/users`
- `/api/v1/roles`
- `/api/v1/permissions`

## APIs consumidas

- Ninguna obligatoria en la version inicial.

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
