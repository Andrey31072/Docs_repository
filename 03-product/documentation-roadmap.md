# Roadmap de construccion documental

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Producto / Arquitectura documental

## Contexto

Este roadmap organiza las historias de usuario documentales en fases logicas. No define estrategia de ramas; usa las ramas existentes del proyecto segun corresponda.

## Fases

| Fase | Nombre | Historias | Objetivo | Salida esperada |
|------|--------|-----------|----------|-----------------|
| Fase 1 | Gobernanza | HU-001, HU-002, HU-003, HU-004 | Establecer reglas, ownership y decision-making | Gobierno documental, arquitectonico, microservicios y datos |
| Fase 2 | Contexto y Dominio | HU-005 | Alinear alcance, lenguaje ubicuo y dominios | Contexto, glosario, mapa de dominio, entidades y eventos |
| Fase 3 | Requerimientos | HU-006 | Crear base verificable de necesidades | Requisitos, HUs funcionales, NFR y trazabilidad |
| Fase 4 | Arquitectura | HU-007 | Documentar solucion, decisiones y vistas | Overview, deployment, cross-cutting, ADRs y diagramas |
| Fase 5 | Datos | HU-008 | Completar modelos, diccionario y migraciones | Modelos globales y por servicio |
| Fase 6 | APIs | HU-009, HU-010 | Formalizar contratos REST y eventos | API contracts, OpenAPI estable y event contracts |
| Fase 7 | Microservicios | HU-011 | Consolidar servicios, relaciones y dependencias | Catalogo, matriz y documentacion por servicio |
| Fase 8 | DevOps | HU-012 | Documentar ambientes y entrega | Environments, CI/CD y setup local |
| Fase 9 | QA | HU-013 | Alinear calidad con requisitos y contratos | Estrategia de pruebas y code review |
| Fase 10 | Operacion | HU-014 | Asegurar soporte, resiliencia y continuidad | Runbooks, observabilidad, incidentes y DR |
| Fase 11 | Capacitacion | HU-015 | Preparar adopcion y transferencia | Manuales y onboarding |

## Orden recomendado

1. Completar Fase 1 antes de crear contenido funcional detallado.
2. Completar Fases 2 y 3 antes de cerrar arquitectura.
3. Completar Fases 4, 5 y 6 antes de implementar integraciones.
4. Completar Fases 7, 8, 9 y 10 antes de pasar a operacion controlada.
5. Completar Fase 11 antes de adopcion por usuarios finales y equipos de soporte.

## Hitos de control

| Hito | Criterio de salida |
|------|--------------------|
| Gobierno listo | DoR/DoD, gobierno y plantillas enlazadas |
| Dominio listo | Entidades, eventos y bounded contexts aprobados |
| Arquitectura lista | ADRs criticos y vistas principales revisadas |
| Contratos listos | APIs/eventos con consumidores y versionado |
| Operacion lista | Runbooks, alertas, backups y DR revisados |

## Recomendaciones finales

- Mantener una fuente canonica por tema y enlazar desde documentos consumidores.
- Evitar copiar definiciones de entidades entre dominios, datos y servicios.
- Crear ADRs para decisiones que cambien dependencias, ownership, comunicacion o despliegue.
- Priorizar `iam-service`, `reference-data-service`, `scheduling-service` y `audit-service` por criticidad transversal.
- Medir avance por documentos en estado `🟢 Estable`, no solo por archivos creados.

## Trazabilidad

- [Historias de usuario documentales](../04-requirements/documentation-user-stories.md)
- [Reporte de hallazgos](../15-project-control/documentation-audit-report.md)
- [Gobierno documental](../00-governance/document-governance.md)
