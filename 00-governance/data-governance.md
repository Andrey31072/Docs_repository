# Gobierno de datos

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Arquitectura de datos

## Contexto

El proyecto usa microservicios con bases de datos independientes. Este documento define ownership, single source of truth, catalogo de datos, diccionario y politicas de sincronizacion.

## Principios

| Principio | Regla |
|-----------|-------|
| Database per service | Cada servicio escribe solo en su base de datos |
| Single source of truth | Una entidad canonica tiene un unico servicio owner |
| Referencias por identidad | Otros servicios guardan identificadores y snapshots minimos, no copias completas |
| Sin joins distribuidos | Las consultas entre dominios se resuelven por API, eventos, proyecciones o reporting controlado |
| Auditoria append-only | `audit-service` no actualiza ni elimina registros de auditoria |
| Calidad medible | Datos criticos deben tener reglas de validacion y ownership |

## Ownership y fuentes canonicas

| Servicio | Base de datos | Entidades owner |
|----------|---------------|-----------------|
| `iam-service` | `iam_db` | `usuario`, `rol`, `permiso`, `sesion`, `token` |
| `reference-data-service` | `ref_db` | `macroregion`, `centro_formacion`, `catalogo`, `estado`, `parametro` |
| `academic-management-service` | `academic_db` | `programa`, `competencia`, `RAP`, `ficha`, `oferta` |
| `training-environment-service` | `env_db` | `ambiente`, `inventario`, `mantenimiento`, `reserva`, `disponibilidad` |
| `scheduling-service` | `scheduling_db` | `horario`, `sesion_clase`, `franja`, `asignacion`, `conflicto` |
| `actors-service` | `actors_db` | `instructor`, `aprendiz`, `empresa`, `etapa_productiva`, `bitacora` |
| `document-service` | `document_db` | `documento`, `version`, `plantilla` |
| `monitoring-service` | `monitoring_db` | `seguimiento_kpi`, `alerta`, `notificacion`, `sesion_seguimiento`, `plan_mejoramiento` |
| `audit-service` | `audit_db` | `auditoria` |

## Catalogo de datos minimo

Cada entidad debe documentar:

| Campo | Descripcion |
|-------|-------------|
| Nombre canonico | Nombre de entidad en singular |
| Servicio owner | Microservicio responsable |
| Base de datos | Persistencia canonica |
| Identificador | Clave primaria o identificador externo |
| Descripcion | Definicion de negocio |
| Clasificacion | Publico, interno, confidencial, sensible |
| Retencion | Tiempo de conservacion |
| Calidad | Validaciones y reglas |
| Consumidores | Servicios o procesos que leen la entidad |

## Diccionario de datos

El diccionario global vive en `06-data/data-dictionary.md`. Los modelos por servicio viven en `09-microservices/services/<servicio>/data-model.md` y deben enlazar al diccionario global cuando exista detalle de atributos.

## Politicas de sincronizacion

| Caso | Patron recomendado | Regla |
|------|--------------------|-------|
| Consulta puntual | REST al servicio owner | Usar timeout y fallback documentado |
| Cambio de estado relevante | Evento de dominio | Publicar evento versionado |
| Catalogos comunes | Cache controlado o replica local de lectura | Definir TTL, invalidacion y owner |
| Reporting | Proyeccion o data mart | No consultar bases transaccionales cruzadas directamente |
| Auditoria | Evento hacia `audit-service` | Registro append-only, sin actualizaciones |

## Restricciones

- Ningun servicio debe escribir en una base de datos que no le pertenece.
- No se permite sincronizacion bidireccional sin ADR.
- No se deben duplicar datos personales o sensibles sin justificacion, clasificacion y control de acceso.
- Las referencias cruzadas deben usar identificadores estables.

## Criterios de actualizacion

Actualizar este documento cuando cambie ownership de entidades, se agregue un servicio, se modifique una politica de sincronizacion o se introduzca una nueva clasificacion de datos.

## Trazabilidad

- [Modelos de datos](../06-data/models.md)
- [Diccionario de datos](../06-data/data-dictionary.md)
- [Matriz de dependencias](../09-microservices/service-dependency-matrix.md)
- [Gobierno arquitectonico](./architecture-governance.md)
