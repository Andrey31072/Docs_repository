# Modelo de datos - iam-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguridad / IAM

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `usuario` | `iam-service` | Identidad autenticable |
| `rol` | `iam-service` | Agrupador de permisos |
| `permiso` | `iam-service` | Accion autorizable |
| `sesion` | `iam-service` | Sesion activa o historica |
| `token` | `iam-service` | Credencial emitida o revocada |

## Relaciones

- Un `usuario` puede tener varios `rol`.
- Un `rol` puede agrupar varios `permiso`.
- Una `sesion` pertenece a un `usuario`.
- Un `token` pertenece a una `sesion` o a un `usuario`, segun el flujo de autenticacion.

## Reglas de negocio

- Los permisos deben evaluarse desde la fuente canonica de IAM.
- Los tokens revocados no pueden ser aceptados por ningun servicio.
- Las sesiones expiradas no deben permitir renovacion sin reautenticacion.

## Restricciones

- No exponer secretos ni hashes en respuestas API.
- No permitir escrituras externas directas sobre `iam_db`.
- Auditar cambios de rol, permiso y token.
