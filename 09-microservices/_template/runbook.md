# Runbook operacional - <nombre-del-servicio>

> Estado: 🔴 Pendiente | Ultima actualizacion: YYYY-MM-DD
> Autor: Por definir | Equipo: Por definir

## Objetivo

Documentar despliegue, rollback, monitoreo, alertas y troubleshooting del microservicio.

## Alcance

Aplica a ambientes `dev`, `qa`, `stage` y `main` segun permisos y procedimientos vigentes.

## Responsables

| Rol | Responsable | Contacto |
|-----|-------------|----------|
| Owner tecnico | Por definir | Por definir |
| Operador | Por definir | Por definir |
| Escalamiento funcional | Por definir | Por definir |

## Despliegue

Describir procedimiento, prerequisitos, variables, migraciones y validaciones.

## Rollback

Describir version anterior, pasos de rollback, validaciones y riesgos de datos.

## Monitoreo

| Indicador | Umbral | Fuente |
|-----------|--------|--------|
| Latencia p95 | Por definir | APM |
| Error rate | Por definir | Logs / metricas |
| Disponibilidad | Por definir | Health check |

## Alertas

| Alerta | Severidad | Sintoma | Accion |
|--------|-----------|---------|--------|
| Por definir | Alta | Por definir | Por definir |

## Troubleshooting

| Sintoma | Verificacion | Accion |
|---------|--------------|--------|
| Error 5xx | Logs con `correlation_id` | Revisar dependencia y reinicio controlado |

## Recuperacion

| Elemento | Valor |
|----------|-------|
| RTO | Por definir |
| RPO | Por definir |
| Backup | Por definir |
| Restauracion | Por definir |

## Criterios de actualizacion

Actualizar por cada release, incidente mayor, cambio de infraestructura, alerta o dependencia critica.

## Trazabilidad

- [Disponibilidad y escalabilidad](../../availability-scalability.md)
- [Observabilidad](../../../13-operations/observability.md)
- [Backup y recuperacion](../../../13-operations/backup-and-recovery.md)
