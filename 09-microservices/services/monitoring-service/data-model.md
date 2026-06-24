# Modelo de datos - monitoring-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguimiento institucional

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `seguimiento_kpi` | `monitoring-service` | Indicador calculado o registrado |
| `alerta` | `monitoring-service` | Condicion que requiere atencion |
| `notificacion` | `monitoring-service` | Mensaje enviado |
| `sesion_seguimiento` | `monitoring-service` | Reunión o actividad de seguimiento |
| `plan_mejoramiento` | `monitoring-service` | Accion correctiva o preventiva |

## Relaciones

- Una `alerta` puede originar una `notificacion`.
- Una `sesion_seguimiento` puede generar `plan_mejoramiento`.
- Un `seguimiento_kpi` puede asociarse a dominio, centro o periodo.

## Reglas de negocio

- KPIs deben indicar fuente, periodo y formula.
- Alertas deben tener severidad y estado.
- Notificaciones deben ser trazables.

## Restricciones

- No reemplazar fuentes canonicas; almacenar indicadores y snapshots necesarios.
- Proteger datos personales en KPIs y notificaciones.
