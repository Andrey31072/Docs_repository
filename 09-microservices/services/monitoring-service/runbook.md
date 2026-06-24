# Runbook operacional - monitoring-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguimiento institucional / Operacion

## Despliegue

Desplegar como servicio stateless para API y workers de consumo de eventos cuando aplique.

## Rollback

Revertir aplicacion preservando alertas, KPIs y planes ya registrados.

## Monitoreo

- Lag de eventos.
- Alertas creadas.
- Notificaciones fallidas.
- Latencia de consulta de KPIs.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Lag alto de eventos | Alta | Revisar consumidores y broker |
| Notificaciones fallidas | Media | Validar canal y reintentos |

## Troubleshooting

Validar consumidores, reglas de KPI, filtros, permisos y logs con `correlation_id`.
