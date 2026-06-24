# Contrato API - <nombre-del-servicio>

> Estado: 🔴 Pendiente | Ultima actualizacion: YYYY-MM-DD
> Autor: Por definir | Equipo: Por definir

## Objetivo

Documentar endpoints, request, response, errores, autenticacion y autorizacion del servicio.

## Alcance

Incluye APIs expuestas por el microservicio y APIs externas consumidas que afecten su comportamiento.

## Responsables

| Rol | Responsable |
|-----|-------------|
| Owner tecnico | Por definir |
| Reviewer API | Por definir |
| QA | Por definir |

## Autenticacion

Describir mecanismo: bearer token, client credentials, API key u otro.

## Autorizacion

Describir roles, permisos y reglas por endpoint.

## Endpoints

| Metodo | Endpoint | Proposito | Auth | Permiso |
|--------|----------|-----------|------|---------|
| GET | `/api/v1/<recurso>` | Por definir | Si | Por definir |

## Request

```json
{
  "campo": "valor"
}
```

## Response

```json
{
  "id": "uuid",
  "estado": "activo"
}
```

## Errores

| Codigo | Caso | Response esperado |
|--------|------|-------------------|
| 400 | Request invalido | `error_code`, `message`, `correlation_id` |
| 401 | No autenticado | `error_code`, `message`, `correlation_id` |
| 403 | No autorizado | `error_code`, `message`, `correlation_id` |
| 404 | No encontrado | `error_code`, `message`, `correlation_id` |
| 409 | Conflicto | `error_code`, `message`, `correlation_id` |

## Dependencias

| API consumida | Servicio destino | Motivo | Fallback |
|---------------|------------------|--------|----------|

## Criterios de actualizacion

Actualizar cuando cambie un endpoint, payload, codigo de error, autenticacion, autorizacion o dependencia.

## Trazabilidad

- OpenAPI formal: `../../../07-api/contracts/openapi/`
- [Gobierno de microservicios](../../../00-governance/microservices-governance.md)
