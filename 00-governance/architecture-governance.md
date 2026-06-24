# Gobierno arquitectonico

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Arquitectura

## Contexto

Este documento define el marco de gobierno para decisiones de arquitectura empresarial, arquitectura de solucion y arquitectura de microservicios del proyecto.

## Objetivo

Asegurar que las decisiones tecnicas sean trazables, revisables y alineadas con dominios funcionales, DDD, Clean Architecture, seguridad, operacion y escalabilidad.

## Alcance

Aplica a cambios de estructura documental, nuevos microservicios, integraciones, decisiones de datos, contratos API, eventos, despliegue, observabilidad, seguridad y resiliencia.

## Principios arquitectonicos

| Principio | Regla aplicable |
|-----------|-----------------|
| Dominio primero | Cada microservicio debe responder a un bounded context claro y a un owner funcional |
| Autonomia del servicio | Cada microservicio debe tener base de datos propia y evitar escrituras directas en datos de otro servicio |
| Contratos explicitos | APIs, eventos y esquemas deben estar documentados antes de integraciones productivas |
| Observabilidad desde el diseno | Logs, metricas, trazas y alertas deben definirse junto con cada servicio |
| Seguridad por defecto | Toda API debe declarar autenticacion, autorizacion, datos sensibles y controles |
| Trazabilidad completa | Toda decision debe enlazar requerimientos, ADR, datos, API, pruebas y runbook |
| Evolucion incremental | La documentacion debe permitir versionado y cambios compatibles |
| Fallos contenidos | Las dependencias entre servicios deben considerar timeouts, retries, idempotencia y circuit breakers |

## Decisiones arquitectonicas

Toda decision significativa debe registrarse como ADR cuando cumpla al menos una condicion:

| Condicion | Ejemplo |
|-----------|---------|
| Crea, divide, fusiona o retira un microservicio | Separar `scheduling-service` de `academic-management-service` |
| Define un patron transversal | Comunicacion por eventos para auditoria |
| Cambia ownership de datos | Mover `centro_formacion` a `reference-data-service` |
| Introduce tecnologia o infraestructura compartida | Broker de eventos, API Gateway, observabilidad |
| Afecta seguridad, resiliencia o operacion | Estrategia de tokens, backups, DR |

Los ADR viven en `05-architecture/decisions/records/` y deben registrarse en el indice de decisiones.

## Ownership por dominio

| Dominio | Microservicio owner | Base de datos | Owner funcional sugerido |
|---------|---------------------|---------------|--------------------------|
| Identidad y acceso | `iam-service` | `iam_db` | Seguridad / IAM |
| Datos de referencia | `reference-data-service` | `ref_db` | Gobierno de datos |
| Gestion academica | `academic-management-service` | `academic_db` | Coordinacion academica |
| Ambientes de formacion | `training-environment-service` | `env_db` | Gestion de ambientes |
| Programacion horaria | `scheduling-service` | `scheduling_db` | Planeacion academica |
| Actores | `actors-service` | `actors_db` | Gestion de actores |
| Documentos | `document-service` | `document_db` | Gestion documental |
| Seguimiento y monitoreo | `monitoring-service` | `monitoring_db` | Seguimiento institucional |
| Auditoria | `audit-service` | `audit_db` | Auditoria / Cumplimiento |

## Proceso de revision

| Paso | Responsable | Evidencia |
|------|-------------|-----------|
| Proponer cambio | Equipo solicitante | Issue, HU o pregunta abierta |
| Evaluar impacto | Arquitectura | ADR propuesto o decision menor documentada |
| Validar datos y contratos | Owners de dominio | Matriz de dependencias, API/event contract |
| Validar operacion | DevOps / Operacion | Runbook, alertas, rollback |
| Aprobar | Arquitectura y owner funcional | Estado de ADR y PR aprobado |

## Criterios de actualizacion

Actualizar este documento cuando se agregue un dominio, cambie un owner, se adopte un patron transversal o se modifique el proceso de decision.

## Trazabilidad

- Fuente de decisiones: [ADRs](../05-architecture/decisions/README.md)
- Microservicios: [Catalogo de servicios](../09-microservices/service-catalog.md)
- Datos: [Gobierno de datos](./data-governance.md)
- Dependencias: [Matriz de dependencias](../09-microservices/service-dependency-matrix.md)
