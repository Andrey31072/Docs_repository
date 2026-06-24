# Contrato API - reference-data-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gobierno de datos

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Lectura para servicios autorizados; escritura solo para roles administradores de datos de referencia.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/catalogos` | Listar catalogos |
| GET | `/api/v1/catalogos/{codigo}` | Consultar catalogo |
| GET | `/api/v1/estados` | Listar estados |
| GET | `/api/v1/parametros/{codigo}` | Consultar parametro |
| GET | `/api/v1/centros-formacion` | Listar centros |

## Request y response

Incluir filtros por vigencia, centro, tipo y codigo cuando aplique.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Filtro invalido |
| 401 | Token invalido |
| 403 | Sin permisos de administracion |
| 404 | Recurso no encontrado |
| 409 | Codigo duplicado |
