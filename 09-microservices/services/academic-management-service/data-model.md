# Modelo de datos - academic-management-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Coordinacion academica

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `programa` | `academic-management-service` | Programa de formacion |
| `competencia` | `academic-management-service` | Competencia asociada al programa |
| `RAP` | `academic-management-service` | Resultado de aprendizaje |
| `ficha` | `academic-management-service` | Grupo academico |
| `oferta` | `academic-management-service` | Oferta de formacion |

## Relaciones

- Un `programa` tiene varias `competencia`.
- Una `competencia` tiene varios `RAP`.
- Una `ficha` se asocia a un `programa`.
- Una `oferta` puede crear o referenciar fichas.

## Reglas de negocio

- Una ficha debe pertenecer a un programa vigente.
- Las competencias y RAP deben mantener trazabilidad curricular.
- Cambios academicos con impacto en horarios deben publicar evento.

## Restricciones

- No duplicar entidades academicas como fuente canonica en otros servicios.
- Referenciar centros y estados desde `reference-data-service`.
