# Runbook operacional - audit-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Auditoria / Cumplimiento / Operacion

## Despliegue

Desplegar consumidores de eventos y API de consulta con acceso restringido a `audit_db`.

## Rollback

Revertir aplicacion sin modificar ni eliminar registros existentes. Validar compatibilidad de consumidores.

## Monitoreo

- Lag de cola de auditoria.
- Eventos procesados.
- Eventos rechazados.
- Errores de escritura append-only.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Lag alto en auditoria | Critica | Revisar broker, consumidores y capacidad |
| Error de escritura en `audit_db` | Critica | Activar incidente de cumplimiento |
| Intento de update/delete | Critica | Bloquear operacion e investigar |

## Troubleshooting

Validar broker, consumidores, permisos de solo insercion, almacenamiento, retencion y logs con `correlation_id`.
