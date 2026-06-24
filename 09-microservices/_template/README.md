# <nombre-del-servicio>

> Este directorio es una PLANTILLA. Copiar a `services/<nombre-servicio>/` solo cuando el servicio exista o este aprobado por arquitectura.
> Estado: 🔴 Pendiente | Ultima actualizacion: YYYY-MM-DD
> Autor: Por definir | Equipo: Por definir

## Proposito

Describir que capacidad de negocio entrega el servicio y por que existe.

## Dominio de negocio

Indicar bounded context, lenguaje ubicuo y owner funcional.

## Responsabilidades

- Responsabilidad 1.
- Responsabilidad 2.
- Responsabilidad 3.

## Dependencias

| Tipo | Dependencia | Uso | Criticidad |
|------|-------------|-----|------------|
| Datos | `<database>` | Persistencia canonica | Alta |
| API consumida | `<servicio>` | `<motivo>` | Media |
| Evento consumido | `<evento>` | `<motivo>` | Media |

## Base de datos

`<database>`

## Eventos publicados

- `<dominio>.<entidad>.<accion>.v1`

## Eventos consumidos

- `<dominio>.<entidad>.<accion>.v1`

## APIs expuestas

- `/api/v1/<recurso>`

## APIs consumidas

- `<servicio-destino>`

## Responsables

| Rol | Responsable |
|-----|-------------|
| Owner funcional | Por definir |
| Owner tecnico | Por definir |
| Data owner | Por definir |
| Operador | Por definir |

## Criterios de actualizacion

Actualizar cuando cambie proposito, ownership, dependencia, base de datos, API, evento o runbook.

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
