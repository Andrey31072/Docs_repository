# Plantillas documentales

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion documental

## Contexto

Este documento define plantillas profesionales para las carpetas documentales del proyecto. Cada plantilla conserva la misma estructura minima y agrega secciones obligatorias segun el tipo de contenido.

## Plantilla base obligatoria

```markdown
# <Titulo del documento>

> Estado: 🔴 Pendiente | Ultima actualizacion: YYYY-MM-DD
> Autor: <nombre> | Equipo: <equipo>

## Objetivo

## Alcance

## Responsables

| Rol | Responsable | Funcion |
|-----|-------------|---------|
| Owner funcional | Por definir | Aprueba contenido de negocio |
| Owner tecnico | Por definir | Valida consistencia tecnica |
| Reviewer | Por definir | Revisa calidad y trazabilidad |

## Dependencias

| Dependencia | Tipo | Impacto |
|-------------|------|---------|

## Contenido

## Secciones obligatorias

## Criterios de actualizacion

## Trazabilidad

| Relacion | Enlace |
|----------|--------|

## Referencias
```

## Templates por carpeta

| Carpeta | Objetivo | Secciones obligatorias | Criterios de actualizacion | Trazabilidad minima |
|---------|----------|------------------------|----------------------------|---------------------|
| `00-governance/` | Definir reglas y controles transversales | Politica, alcance, roles, proceso, excepciones, cumplimiento | Cambio de regla, owner o proceso | README, CONTRIBUTING, DoR, DoD |
| `01-context/` | Explicar contexto institucional y alcance | Problema, actores, alcance, fuera de alcance, supuestos, glosario | Cambio de alcance o termino de negocio | Producto, dominio, requerimientos |
| `02-domain/` | Modelar dominio y bounded contexts | Contextos, entidades, reglas, eventos, invariantes, lenguaje ubicuo | Nuevo dominio, entidad o regla | Microservicios, datos, eventos |
| `03-product/` | Gestionar vision y roadmap | Vision, objetivos, epicas, backlog, releases, indicadores | Cambio de prioridad o fase | Requerimientos, roadmap documental |
| `04-requirements/` | Documentar requisitos y HUs | Requisito, HU, prioridad, dependencias, criterios, pruebas, trazabilidad | Cambio funcional o no funcional | Arquitectura, API, QA, operacion |
| `05-architecture/` | Describir arquitectura y decisiones | Vistas, componentes, despliegue, atributos de calidad, ADR, riesgos | Nueva decision o cambio de patron | ADR, microservicios, datos, DevOps |
| `06-data/` | Gobernar modelos y diccionario | Entidades, owner, atributos, clasificacion, relaciones, retencion | Cambio de entidad, atributo o politica | Gobierno de datos, microservicios |
| `07-api/` | Estandarizar APIs | Recurso, endpoint, seguridad, request, response, errores, version | Cambio de contrato | Microservicio, OpenAPI, QA |
| `08-uml/` | Registrar diagramas | Tipo, fuente editable, exportacion, owner, fecha, enlace consumidor | Cambio de diagrama o vista | Arquitectura, dominio, requerimientos |
| `09-microservices/` | Documentar servicios | README, datos, API, eventos, runbook, dependencias | Cambio de servicio, contrato o operacion | Catalogo, matriz, ADR |
| `10-devops/` | Documentar entrega e infraestructura | Ambientes, variables, pipeline, despliegue, rollback, seguridad | Cambio de ambiente o pipeline | Runbooks, operaciones |
| `11-quality/` | Definir QA | Estrategia, niveles, criterios, cobertura, evidencias, defectos | Cambio de criterio de calidad | HUs, APIs, runbooks |
| `12-ux-ui/` | Documentar experiencia | Flujos, pantallas, navegacion, design system, accesibilidad | Cambio de flujo o componente | Requerimientos, producto |
| `13-operations/` | Operar el sistema | SLO, monitoreo, incidentes, backups, DR, soporte | Cambio de operacion o incidente mayor | Runbooks, DevOps, arquitectura |
| `14-training/` | Capacitar usuarios y equipos | Audiencia, prerrequisitos, pasos, escenarios, evaluacion | Cambio funcional u operativo | Producto, operaciones |
| `15-project-control/` | Controlar riesgos y trabajo | Riesgos, dependencias, preguntas, backlog tecnico, decisiones | Cambio de estado o prioridad | Todas las areas afectadas |
| `99-archive/` | Preservar historia | Motivo, origen, reemplazo, fecha, owner | Al archivar o deprecar | Documento reemplazado, changelog |

## Plantilla de trazabilidad

```markdown
## Trazabilidad

| Elemento | Enlace | Estado |
|----------|--------|--------|
| Requerimiento | ../04-requirements/<archivo>.md | Por definir |
| ADR | ../05-architecture/decisions/records/<adr>.md | Por definir |
| Microservicio | ../09-microservices/services/<servicio>/README.md | Por definir |
| API | ../09-microservices/services/<servicio>/api-contract.md | Por definir |
| Datos | ../09-microservices/services/<servicio>/data-model.md | Por definir |
| Pruebas | ../11-quality/<archivo>.md | Por definir |
| Operacion | ../09-microservices/services/<servicio>/runbook.md | Por definir |
```

## Responsables

| Rol | Responsabilidad |
|-----|-----------------|
| Autor | Crear o actualizar el contenido |
| Owner documental | Asegurar vigencia y aprobaciones |
| Arquitectura | Validar coherencia tecnica y decisiones |
| QA | Validar criterios de aceptacion y evidencias |
| DevOps / Operacion | Validar despliegue, monitoreo y recuperacion |

## Dependencias

- [Reglas de documentacion](./documentation-rules.md)
- [Gobierno documental](./document-governance.md)
- [Definition of Ready](./definition-of-ready.md)
- [Definition of Done](./definition-of-done.md)

## Criterios de actualizacion

Actualizar cuando se cree una nueva carpeta, cambie una seccion obligatoria, cambien criterios de trazabilidad o se detecte una brecha documental recurrente.

## Referencias

- [CONTRIBUTING](../CONTRIBUTING.md)
- [Reporte de hallazgos](../15-project-control/documentation-audit-report.md)
