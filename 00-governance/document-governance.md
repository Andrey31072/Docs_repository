# Gobierno documental

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion documental

## Contexto

Este documento complementa las reglas existentes de documentacion con estados, versionado, aprobaciones, revisiones y trazabilidad.

## Estados documentales

| Estado | Uso | Responsable de avance |
|--------|-----|-----------------------|
| 🔴 Pendiente | Documento creado o identificado, sin contenido validado | Autor |
| 🟡 En progreso | Documento con contenido parcial o en revision | Autor y reviewers |
| 🟢 Estable | Documento revisado, aprobado y vigente | Owner documental |
| ⚫ Deprecado | Documento reemplazado o no vigente | Owner documental |

## Versionado documental

| Elemento | Regla |
|----------|-------|
| Fecha | Todo documento debe indicar ultima actualizacion |
| Cambios relevantes | Registrar en `CHANGELOG.md` cuando afecten varias areas |
| ADR | Versionar por nuevo ADR; no sobrescribir decisiones historicas |
| Contratos API/eventos | Versionar cuando cambie el contrato externo |
| Templates | Mantener criterios de actualizacion y trazabilidad |

## Aprobaciones

Cada documento critico debe incluir una tabla de aprobaciones cuando pase a estable:

| Rol | Nombre | Fecha | Evidencia |
|-----|--------|-------|-----------|
| Autor | Por definir | YYYY-MM-DD | PR |
| Reviewer tecnico | Por definir | YYYY-MM-DD | Comentario de revision |
| Owner funcional | Por definir | YYYY-MM-DD | Aprobacion |
| Arquitectura | Por definir | YYYY-MM-DD | Aprobacion |

## Revisiones periodicas

| Tipo de documento | Frecuencia minima | Responsable |
|-------------------|-------------------|-------------|
| Gobierno | Trimestral | Arquitectura / Gestion documental |
| Arquitectura y ADR | Por cambio significativo | Arquitectura |
| Datos | Mensual o por cambio de entidad | Arquitectura de datos |
| APIs y eventos | Por version | Desarrollo / QA |
| Runbooks | Por release o incidente mayor | DevOps / Operacion |
| Capacitacion | Por cambio funcional | Producto / Soporte |

## Criterios de calidad documental

- Debe tener objetivo, alcance, responsables, dependencias y trazabilidad.
- Debe enlazar su fuente canonica en vez de duplicar definiciones.
- Debe declarar estado real de madurez.
- Debe ser compatible con GitHub Markdown.
- Debe evitar secretos, credenciales y datos sensibles.
- Debe tener criterios de actualizacion claros.

## Criterios de actualizacion

Actualizar este documento cuando cambien estados, aprobaciones, flujo de revision, frecuencia de mantenimiento o criterios de calidad.

## Trazabilidad

- [Reglas de documentacion](./documentation-rules.md)
- [Definition of Ready](./definition-of-ready.md)
- [Definition of Done](./definition-of-done.md)
- [Plantillas documentales](./document-templates.md)
