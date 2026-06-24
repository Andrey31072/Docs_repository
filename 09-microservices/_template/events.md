# Contrato de eventos - <nombre-del-servicio>

> Estado: 🔴 Pendiente | Ultima actualizacion: YYYY-MM-DD
> Autor: Por definir | Equipo: Por definir

## Objetivo

Documentar eventos publicados y consumidos por el servicio, incluyendo producer, consumer, payload, esquema y versionado.

## Alcance

Incluye eventos de dominio, integracion, auditoria y notificacion que entren o salgan del servicio.

## Responsables

| Rol | Responsable |
|-----|-------------|
| Owner tecnico | Por definir |
| Reviewer arquitectura | Por definir |
| Consumer owner | Por definir |

## Eventos publicados

| Evento | Producer | Consumers | Payload minimo | Version |
|--------|----------|-----------|----------------|---------|
| `<dominio>.<entidad>.<accion>.v1` | `<servicio>` | Por definir | `event_id`, `occurred_at`, `correlation_id` | v1 |

## Eventos consumidos

| Evento | Producer | Uso | Idempotencia |
|--------|----------|-----|--------------|
| `<dominio>.<entidad>.<accion>.v1` | `<servicio>` | Por definir | Por definir |

## Esquema base

```json
{
  "event_id": "uuid",
  "producer": "<servicio>",
  "schema_version": "1.0.0",
  "occurred_at": "YYYY-MM-DDTHH:mm:ssZ",
  "correlation_id": "uuid",
  "payload": {}
}
```

## Versionado

Cambios compatibles conservan el mismo evento. Cambios incompatibles crean una nueva version con sufijo `.v2`.

## Criterios de actualizacion

Actualizar cuando cambie producer, consumer, payload, esquema, version o garantia de entrega.

## Trazabilidad

- [Eventos de dominio](../../../02-domain/domain-events.md)
- [Matriz de dependencias](../../service-dependency-matrix.md)
