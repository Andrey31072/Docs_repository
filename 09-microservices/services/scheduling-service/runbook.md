# Runbook operacional - scheduling-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Planeacion academica / Operacion

## Despliegue

Desplegar como servicio stateless con acceso a `scheduling_db` y dependencias configuradas por ambiente.

## Rollback

Revertir aplicacion validando que asignaciones y reservas externas queden consistentes.

## Monitoreo

- Conflictos detectados.
- Latencia de creacion de horario.
- Errores 409.
- Fallas de dependencias externas.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Aumento de conflictos criticos | Alta | Revisar reglas y disponibilidad |
| Falla de dependencia de ambientes | Critica | Activar degradacion o pausa de asignacion |

## Troubleshooting

Validar fichas, instructores, ambientes, franjas, reservas, idempotencia y trazas con `correlation_id`.
