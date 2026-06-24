# Modelo de datos - actors-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gestion de actores

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `instructor` | `actors-service` | Instructor asociado a formacion |
| `aprendiz` | `actors-service` | Aprendiz en formacion |
| `empresa` | `actors-service` | Empresa asociada |
| `etapa_productiva` | `actors-service` | Etapa productiva del aprendiz |
| `bitacora` | `actors-service` | Registro de seguimiento |

## Relaciones

- Un `aprendiz` puede tener una `etapa_productiva`.
- Una `empresa` puede estar asociada a varias etapas productivas.
- Una `bitacora` pertenece a un aprendiz o etapa.

## Reglas de negocio

- Datos personales deben tener acceso restringido.
- Cambios de disponibilidad de instructor deben publicar evento.
- Bitacoras deben conservar trazabilidad temporal.

## Restricciones

- No duplicar credenciales de usuario; referenciar `iam-service`.
- Referenciar catalogos y estados desde `reference-data-service`.
