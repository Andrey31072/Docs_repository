# Contrato API - scheduling-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Planeacion academica

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Roles de planeacion para crear o modificar horarios; lectura para actores autorizados.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/horarios` | Listar horarios |
| POST | `/api/v1/horarios` | Crear horario |
| POST | `/api/v1/asignaciones` | Crear asignacion |
| GET | `/api/v1/conflictos` | Consultar conflictos |
| POST | `/api/v1/sesiones-clase/{id}/cancel` | Cancelar sesion |

## Request y response

Incluir ficha, instructor, ambiente, franja, fecha, estado e `idempotency_key`.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Datos de programacion invalidos |
| 401 | Token invalido |
| 403 | Sin permiso |
| 404 | Recurso no encontrado |
| 409 | Conflicto de instructor, ambiente o franja |
