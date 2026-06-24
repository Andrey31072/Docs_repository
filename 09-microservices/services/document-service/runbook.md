# Runbook operacional - document-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion documental / Operacion

## Despliegue

Desplegar como servicio stateless con acceso a `document_db` y almacenamiento documental si aplica.

## Rollback

Revertir aplicacion sin eliminar versiones ya creadas.

## Monitoreo

- Versiones creadas.
- Errores de permisos.
- Errores de almacenamiento.
- Latencia de consulta documental.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Error al crear version | Alta | Validar `document_db` y almacenamiento |
| Incremento de 403 | Media | Revisar permisos y reglas IAM |

## Troubleshooting

Validar owner, permisos, version, checksum, conectividad y logs con `correlation_id`.
