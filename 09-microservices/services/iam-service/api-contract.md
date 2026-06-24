# Contrato API - iam-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguridad / IAM

## Autenticacion

Bearer token para endpoints protegidos. Los endpoints de login y refresh aplican controles especificos.

## Autorizacion

Basada en roles y permisos administrados por `iam-service`.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| POST | `/api/v1/auth/login` | Crear sesion y emitir token |
| POST | `/api/v1/auth/refresh` | Renovar token |
| POST | `/api/v1/auth/logout` | Revocar sesion/token |
| GET | `/api/v1/users/{id}` | Consultar usuario |
| GET | `/api/v1/permissions/evaluate` | Evaluar permiso |

## Request y response

Documentar campos obligatorios, formatos, ejemplos y codigos HTTP antes de estabilizar el contrato OpenAPI.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Request invalido |
| 401 | Credenciales invalidas o token expirado |
| 403 | Permiso insuficiente |
| 404 | Usuario no encontrado |
| 409 | Conflicto de estado |
