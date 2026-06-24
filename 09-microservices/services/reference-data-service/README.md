# reference-data-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gobierno de datos

## Proposito

Administrar datos maestros, catalogos, estados y parametros compartidos por los demas servicios.

## Dominio de negocio

Datos de referencia.

## Responsabilidades

- Administrar `macroregion`, `centro_formacion`, `catalogo`, `estado` y `parametro`.
- Proveer datos de referencia versionables y cacheables.
- Controlar vigencia de catalogos.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `ref_db` | Persistencia canonica |
| Consumidores | Todos los servicios | Catalogos, estados y parametros |

## Base de datos

`ref_db`

## Eventos publicados

- `reference.catalogo.updated.v1`
- `reference.parametro.updated.v1`
- `reference.centro-formacion.updated.v1`

## Eventos consumidos

- Ninguno obligatorio en la version inicial.

## APIs expuestas

- `/api/v1/catalogos`
- `/api/v1/estados`
- `/api/v1/parametros`
- `/api/v1/centros-formacion`

## APIs consumidas

- Ninguna obligatoria en la version inicial.

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
