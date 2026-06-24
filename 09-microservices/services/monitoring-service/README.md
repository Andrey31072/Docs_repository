# monitoring-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguimiento institucional

## Proposito

Gestionar KPIs, alertas, notificaciones, sesiones de seguimiento y planes de mejoramiento.

## Dominio de negocio

Seguimiento y monitoreo.

## Responsabilidades

- Administrar `seguimiento_kpi`, `alerta`, `notificacion`, `sesion_seguimiento` y `plan_mejoramiento`.
- Consumir eventos e indicadores de otros dominios.
- Emitir alertas y notificaciones.

## Dependencias

| Tipo | Dependencia | Uso |
|------|-------------|-----|
| Datos | `monitoring_db` | Persistencia canonica |
| Eventos | Servicios de dominio | KPIs y alertas |
| API consumida | `iam-service` | Permisos |

## Base de datos

`monitoring_db`

## Eventos publicados

- `monitoring.alerta.created.v1`
- `monitoring.notificacion.sent.v1`
- `monitoring.plan-mejoramiento.created.v1`

## Eventos consumidos

- Eventos relevantes de scheduling, academic, actors, environment y document.

## APIs expuestas

- `/api/v1/kpis`
- `/api/v1/alertas`
- `/api/v1/notificaciones`
- `/api/v1/sesiones-seguimiento`
- `/api/v1/planes-mejoramiento`

## APIs consumidas

- `iam-service`
- APIs de dominios cuando se requiera consulta complementaria.

## Trazabilidad

- [Modelo de datos](./data-model.md)
- [Contrato API](./api-contract.md)
- [Eventos](./events.md)
- [Runbook](./runbook.md)
