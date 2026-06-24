# Runbook operacional - academic-management-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Coordinacion academica / Operacion

## Despliegue

Desplegar como servicio stateless con acceso a `academic_db`.

## Rollback

Revertir aplicacion y validar migraciones de estructura curricular.

## Monitoreo

- Latencia de consultas academicas.
- Errores por vigencia o conflictos.
- Eventos academicos publicados.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Falla de consulta de ficha | Alta | Validar `academic_db` y dependencias |
| Error publicando cambio academico | Media | Reintentar evento y revisar broker |

## Troubleshooting

Validar vigencia de programa, ficha, oferta, estados de referencia y logs con `correlation_id`.
