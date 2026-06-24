# Contrato API - document-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion documental

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Permisos por tipo de documento, accion y owner.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/documentos` | Listar documentos |
| POST | `/api/v1/documentos` | Crear documento |
| GET | `/api/v1/documentos/{id}/versiones` | Listar versiones |
| POST | `/api/v1/documentos/{id}/versiones` | Crear version |
| GET | `/api/v1/plantillas` | Listar plantillas |

## Request y response

Incluir metadatos, estado, owner, clasificacion, referencia externa y checksum cuando aplique.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Metadatos invalidos |
| 401 | Token invalido |
| 403 | Sin permiso |
| 404 | Documento no encontrado |
| 409 | Conflicto de version |
