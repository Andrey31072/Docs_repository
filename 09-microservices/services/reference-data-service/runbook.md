# Runbook operacional - reference-data-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gobierno de datos / Operacion

## Despliegue

Desplegar como servicio stateless con acceso a `ref_db`.

## Rollback

Revertir aplicacion y validar compatibilidad de cambios en catalogos o parametros.

## Monitoreo

- Latencia de consulta de catalogos.
- Errores 4xx/5xx.
- Eventos de actualizacion publicados.
- Uso de cache por consumidores.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Falla en consulta de catalogos | Alta | Verificar `ref_db` y cache |
| Error publicando evento de actualizacion | Media | Reintentar y validar broker |

## Troubleshooting

Validar vigencia de datos, parametros activos, conectividad a `ref_db` y trazas por `correlation_id`.
