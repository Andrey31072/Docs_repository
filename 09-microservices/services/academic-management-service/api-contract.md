# Contrato API - academic-management-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Coordinacion academica

## Autenticacion

Bearer token emitido por `iam-service`.

## Autorizacion

Roles academicos para escritura; consumidores autorizados para lectura.

## Endpoints

| Metodo | Endpoint | Proposito |
|--------|----------|-----------|
| GET | `/api/v1/programas` | Listar programas |
| GET | `/api/v1/programas/{id}` | Consultar programa |
| GET | `/api/v1/fichas/{id}` | Consultar ficha |
| GET | `/api/v1/ofertas` | Listar ofertas |
| POST | `/api/v1/ofertas` | Crear oferta |

## Request y response

Documentar identificadores de programa, ficha, competencia, RAP, centro y estado.

## Errores

| Codigo | Caso |
|--------|------|
| 400 | Datos academicos invalidos |
| 401 | Token invalido |
| 403 | Sin permiso academico |
| 404 | Entidad no encontrada |
| 409 | Conflicto de vigencia o duplicidad |
