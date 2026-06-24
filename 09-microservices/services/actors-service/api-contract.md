# Contrato API - actors-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de actores

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Roles academicos y administrativos segun sensibilidad de datos.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/instructores` | Listar instructores |
| GET | `/api/v1/instructores/{id}/disponibilidad` | Consultar disponibilidad |
| GET | `/api/v1/aprendices/{id}` | Consultar aprendiz |
| POST | `/api/v1/bitacoras` | Crear bitacora |
| GET | `/api/v1/empresas` | Listar empresas |

## Request y response

Documentar datos personales, clasificacion, mascaramiento y permisos requeridos.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Datos invalidos |
| 401 | Token invalido |
| 403 | Acceso restringido |
| 404 | Actor no encontrado |
| 409 | Conflicto de estado |
