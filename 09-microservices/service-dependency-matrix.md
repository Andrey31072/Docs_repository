# Matriz de relaciones entre microservicios

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Arquitectura de solucion

## Contexto

Esta matriz identifica dependencias, comunicacion, datos compartidos e integraciones entre microservicios. Debe validarse con ADRs, contratos API y eventos antes de implementacion.

## Dependencias

| Servicio origen | Servicio destino | Motivo de dependencia | Tipo |
|-----------------|------------------|-----------------------|------|
| `scheduling-service` | `iam-service` | Validar usuario, rol y permisos para acciones de programacion | REST |
| `scheduling-service` | `reference-data-service` | Consultar centros, estados, parametros y catalogos | REST / Cache |
| `scheduling-service` | `academic-management-service` | Consultar fichas, programas, competencias, RAP y ofertas | REST |
| `scheduling-service` | `training-environment-service` | Consultar disponibilidad y reservar ambientes | REST / Evento |
| `scheduling-service` | `actors-service` | Consultar disponibilidad y asignacion de instructores/aprendices | REST |
| `training-environment-service` | `reference-data-service` | Clasificar ambientes, estados y parametros | REST / Cache |
| `academic-management-service` | `reference-data-service` | Usar catalogos y estados academicos | REST / Cache |
| `actors-service` | `reference-data-service` | Usar catalogos, estados y centros | REST / Cache |
| `document-service` | `iam-service` | Validar permisos sobre documentos y plantillas | REST |
| `document-service` | `academic-management-service` | Asociar documentos a programas, fichas u ofertas | REST |
| `monitoring-service` | `scheduling-service` | Obtener indicadores de horarios, conflictos y asignaciones | Evento / REST |
| `monitoring-service` | `actors-service` | Obtener indicadores de actores y seguimiento | Evento / REST |
| `monitoring-service` | `academic-management-service` | Obtener indicadores academicos | Evento / REST |
| `audit-service` | Todos | Registrar eventos auditables append-only | Evento / Mensajeria |

## Comunicacion

| Patron | Uso recomendado | Servicios principales |
|--------|-----------------|----------------------|
| REST sincrono | Consulta puntual de datos canonicos | IAM, reference, academic, actors, environments |
| Eventos | Cambios de estado relevantes y auditoria | Todos hacia monitoring/audit cuando aplique |
| Mensajeria async | Procesos desacoplados, notificaciones, auditoria | monitoring-service, audit-service |
| Cache de referencia | Catalogos de baja volatilidad | Servicios consumidores de `reference-data-service` |

## Datos compartidos y referencias cruzadas

| Dato | Owner canonico | Consumidores | Regla |
|------|----------------|--------------|-------|
| `usuario`, `rol`, `permiso` | `iam-service` | Todos | No duplicar permisos; validar por token o API |
| `centro_formacion`, `catalogo`, `estado`, `parametro` | `reference-data-service` | Todos | Cache permitido con TTL documentado |
| `programa`, `competencia`, `RAP`, `ficha`, `oferta` | `academic-management-service` | scheduling, document, monitoring | Referenciar por ID estable |
| `ambiente`, `disponibilidad` | `training-environment-service` | scheduling, monitoring | Reservas deben ser consistentes e idempotentes |
| `instructor`, `aprendiz`, `empresa` | `actors-service` | scheduling, monitoring, document | Evitar duplicar datos personales |
| `horario`, `sesion_clase`, `asignacion`, `conflicto` | `scheduling-service` | monitoring, document, audit | Publicar cambios relevantes |
| `documento`, `version`, `plantilla` | `document-service` | academic, actors, monitoring | Versionar documentos |
| `auditoria` | `audit-service` | Cumplimiento | Append-only, sin actualizaciones |

## Riesgos de acoplamiento

| Riesgo | Mitigacion |
|--------|------------|
| Dependencias sincronas excesivas sobre `reference-data-service` | Cache con TTL, circuit breaker y degradacion controlada |
| `scheduling-service` como orquestador demasiado acoplado | Definir APIs pequenas, eventos de estado e idempotencia |
| Duplicidad de datos personales | Mantener owner en IAM/actors y snapshots minimos |
| Auditoria bloqueando transacciones | Publicacion async con cola y reintentos |

## Criterios de actualizacion

Actualizar cuando se agregue una dependencia, cambie un contrato, se cree un evento, cambie ownership de datos o se incorpore un nuevo microservicio.

## Trazabilidad

- [Gobierno de microservicios](../00-governance/microservices-governance.md)
- [Gobierno de datos](../00-governance/data-governance.md)
- [Catalogo de servicios](./service-catalog.md)
