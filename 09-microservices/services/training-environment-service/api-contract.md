# Contrato API - training-environment-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de ambientes

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Lectura para programacion; escritura para gestion de ambientes y procesos autorizados.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/ambientes` | Listar ambientes |
| GET | `/api/v1/disponibilidades` | Consultar disponibilidad |
| POST | `/api/v1/reservas` | Crear reserva |
| DELETE | `/api/v1/reservas/{id}` | Cancelar reserva |
| POST | `/api/v1/mantenimientos` | Registrar mantenimiento |

## Request y response

Incluir `ambiente_id`, franja temporal, centro, capacidad, `idempotency_key` y estado.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Franja invalida |
| 401 | Token invalido |
| 403 | Sin permiso |
| 404 | Ambiente no encontrado |
| 409 | Conflicto de reserva o mantenimiento |
