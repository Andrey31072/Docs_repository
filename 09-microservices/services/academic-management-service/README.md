# academic-management-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Coordinacion academica

## Proposito

Gestionar la estructura academica requerida para programar y hacer seguimiento a la formacion.

## Dominio de negocio

Gestion academica.

## Responsabilidades

- Administrar `programa`, `competencia`, `RAP`, `ficha` y `oferta`.
- Proveer informacion academica canonica a programacion, documentos y monitoreo.
- Publicar cambios academicos relevantes.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `academic_db` | Persistencia canonica |
| API consumida | `reference-data-service` | Estados, catalogos y centros |

## Base de datos

`academic_db`

## Eventos publicados

- `academic.programa.updated.v1`
- `academic.ficha.created.v1`
- `academic.oferta.published.v1`

## Eventos consumidos

- `reference.catalogo.updated.v1` cuando afecte catalogos academicos.

## APIs expuestas

- `/api/v1/programas`
- `/api/v1/competencias`
- `/api/v1/raps`
- `/api/v1/fichas`
- `/api/v1/ofertas`

## APIs consumidas

- `reference-data-service`

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
