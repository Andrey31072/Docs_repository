# Modelo de datos - reference-data-service

> Estado: 🟡 En progreso | Ultima actualizacion: 2026-06-21
> Autor: Codex | Equipo: Gobierno de datos

## Entidades

| Entidad | Ownership | Descripcion |
|---------|-----------|-------------|
| `macroregion` | `reference-data-service` | Agrupacion territorial |
| `centro_formacion` | `reference-data-service` | Centro de formacion SENA |
| `catalogo` | `reference-data-service` | Lista de valores controlada |
| `estado` | `reference-data-service` | Estado reutilizable |
| `parametro` | `reference-data-service` | Configuracion de negocio |

## Relaciones

- Una `macroregion` agrupa varios `centro_formacion`.
- Un `catalogo` contiene valores y puede asociarse con `estado`.
- Un `parametro` puede aplicar globalmente o por centro.

## Reglas de negocio

- Catalogos y parametros deben tener vigencia.
- Los consumidores pueden cachear datos con TTL documentado.
- Cambios relevantes deben publicar evento.

## Restricciones

- Los datos de referencia no se duplican como fuente canonica en otros servicios.
- Los consumidores solo guardan identificadores o snapshots justificados.
