# Runbook operacional - training-environment-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de ambientes / Operacion

## Despliegue

Desplegar como servicio stateless con control transaccional sobre `env_db`.

## Rollback

Revertir aplicacion sin perder reservas confirmadas. Validar migraciones antes de rollback.

## Monitoreo

- Conflictos de reserva.
- Latencia de consulta de disponibilidad.
- Reservas creadas/canceladas.
- Eventos pendientes.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Aumento de conflictos 409 | Alta | Revisar concurrencia y franjas |
| Falla al crear reserva | Critica | Revisar `env_db` y estado de ambiente |

## Troubleshooting

Validar disponibilidad, mantenimiento activo, idempotency key, transacciones y logs con `correlation_id`.
