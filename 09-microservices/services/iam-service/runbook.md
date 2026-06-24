# Runbook operacional - iam-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Seguridad / IAM / Operacion

## Despliegue

Desplegar como servicio stateless con conexion segura a `iam_db`.

## Rollback

Revertir version de aplicacion y validar compatibilidad de migraciones de tokens, roles y permisos.

## Monitoreo

- Tasa de login exitoso/fallido.
- Latencia de validacion de permisos.
- Tokens revocados.
- Errores 401/403.

## Alertas

| Alerta | Severidad | Accion |
|--------|-----------|--------|
| Incremento anormal de 401 | Alta | Revisar autenticacion y expiracion de tokens |
| Falla de conexion a `iam_db` | Critica | Activar procedimiento de incidente |

## Troubleshooting

Validar health check, conectividad a base de datos, expiracion de tokens, reloj del sistema y logs con `correlation_id`.
