# Contrato API - monitoring-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguimiento institucional

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Lectura y gestion segun rol institucional y alcance de datos.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/kpis` | Consultar indicadores |
| GET | `/api/v1/alertas` | Listar alertas |
| POST | `/api/v1/notificaciones` | Enviar notificacion |
| POST | `/api/v1/sesiones-seguimiento` | Crear sesion de seguimiento |
| POST | `/api/v1/planes-mejoramiento` | Crear plan |

## Request y response

Incluir fuente, periodo, severidad, estado, destinatario y referencias de dominio.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Filtro o payload invalido |
| 401 | Token invalido |
| 403 | Sin permiso |
| 404 | Indicador o alerta no encontrado |
| 409 | Estado incompatible |
