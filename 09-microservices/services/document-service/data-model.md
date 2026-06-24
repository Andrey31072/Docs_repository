# Modelo de datos - document-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion documental

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `documento` | `document-service` | Documento gestionado |
| `version` | `document-service` | Version historica de documento |
| `plantilla` | `document-service` | Estructura reusable |

## Relaciones

- Un `documento` tiene una o mas `version`.
- Una `plantilla` puede originar varios `documento`.
- Un `documento` puede referenciar entidades externas por ID.

## Reglas de negocio

- Las versiones no deben sobrescribirse.
- Todo documento debe tener owner, estado y trazabilidad.
- Cambios de plantilla deben versionarse.

## Restricciones

- No almacenar permisos como fuente canonica; consultar `iam-service`.
- Documentos sensibles requieren clasificacion y control de acceso.
