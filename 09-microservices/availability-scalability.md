# Disponibilidad y escalabilidad

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Arquitectura / Operacion

## Contexto

Este documento valida que la documentacion soporte escalamiento horizontal, alta disponibilidad, resiliencia, tolerancia a fallos y recuperacion ante desastres para una arquitectura de microservicios.

## Recomendaciones transversales

| Capacidad | Recomendacion documental |
|-----------|--------------------------|
| Escalamiento horizontal | Cada runbook debe indicar si el servicio es stateless, limites de concurrencia, afinidad de sesion y recursos minimos |
| Alta disponibilidad | Documentar replicas minimas, health checks, readiness checks y estrategia multi-zona cuando exista |
| Resiliencia | Definir timeouts, retries, circuit breakers, bulkheads e idempotencia por dependencia |
| Tolerancia a fallos | Documentar fallback por dependencia critica y comportamiento degradado |
| Recuperacion ante desastres | Documentar RTO, RPO, backups, restauracion y prueba de recuperacion por base de datos |
| Observabilidad | Definir SLI, SLO, alertas y dashboards por servicio |
| Datos | Documentar backups por base, retencion, restauracion y consistencia de eventos |

## Validacion por servicio

| Servicio | Escalamiento | HA | DR | Riesgo principal | Recomendacion |
|----------|--------------|----|----|------------------|---------------|
| `iam-service` | Horizontal si sesiones/tokens no dependen de memoria local | Alta | RPO bajo | Punto critico de autenticacion | Replicas, cache distribuido, rotacion de tokens y alertas de auth |
| `reference-data-service` | Horizontal con cache | Alta | RPO medio | Saturacion por consultas comunes | Cache con TTL, invalidacion y read replicas si aplica |
| `academic-management-service` | Horizontal | Media/Alta | RPO medio | Cambios academicos afectan scheduling | Eventos de cambios academicos e idempotencia |
| `training-environment-service` | Horizontal con control de concurrencia | Alta | RPO bajo para reservas | Doble reserva de ambientes | Bloqueos transaccionales, idempotency key y eventos |
| `scheduling-service` | Horizontal con operaciones idempotentes | Alta | RPO bajo | Conflictos y consistencia de horarios | Validacion atomica, colas para procesos largos y rollback funcional |
| `actors-service` | Horizontal | Media/Alta | RPO medio | Datos personales y disponibilidad | Controles de acceso y eventos de disponibilidad |
| `document-service` | Horizontal | Media/Alta | RPO bajo para documentos | Versiones y almacenamiento | Versionado, checksum, backups de metadatos y binarios |
| `monitoring-service` | Horizontal para ingesta | Media | RPO medio | Perdida de metricas/eventos | Buffer async, retencion y reprocesamiento |
| `audit-service` | Horizontal para ingesta append-only | Alta | RPO muy bajo | Perdida o alteracion de auditoria | Cola durable, almacenamiento inmutable y alertas de lag |

## Minimos para runbooks

Cada runbook debe declarar:

- Comando o procedimiento de despliegue.
- Procedimiento de rollback.
- Health check y readiness check.
- SLI/SLO del servicio.
- Alertas y umbrales.
- Dependencias criticas.
- Procedimientos de troubleshooting.
- Backups, RTO y RPO.
- Contactos de owner funcional, tecnico y operador.

## Criterios de actualizacion

Actualizar cuando cambie infraestructura, patron de despliegue, SLO, criticidad, dependencia o politica de recuperacion.

## Trazabilidad

- [Runbooks de microservicios](./services/)
- [Observabilidad](../13-operations/observability.md)
- [Backup y recuperacion](../13-operations/backup-and-recovery.md)
- [Matriz de dependencias](./service-dependency-matrix.md)
