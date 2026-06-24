# Runbook operacional - actors-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de actores / Operacion

## Despliegue

Desplegar como servicio stateless con acceso a `actors_db`.

## Rollback

Revertir aplicacion validando compatibilidad con datos personales y bitacoras.

## Monitoreo

- Latencia de consulta de instructores.
- Errores de autorizacion.
- Eventos de disponibilidad.
- Creacion de bitacoras.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Accesos denegados anormales | Alta | Revisar permisos y posibles errores de integracion |
| Falla de consulta de disponibilidad | Alta | Validar `actors_db` y filtros |

## Troubleshooting

Validar permisos, clasificacion de datos, estado del actor, disponibilidad y logs con `correlation_id`.
