# Contrato API - audit-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Auditoria / Cumplimiento

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Solo roles de auditoria, cumplimiento o administracion autorizada pueden consultar registros.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/auditorias` | Consultar registros auditables |
| GET | `/api/v1/auditorias/{id}` | Consultar registro especifico |

## Request y response

Filtros permitidos: servicio, entidad, accion, usuario, rango temporal y correlation id.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Filtros invalidos |
| 401 | Token invalido |
| 403 | Sin permiso de auditoria |
| 404 | Registro no encontrado |
| 405 | Escritura o actualizacion no permitida por API publica |
