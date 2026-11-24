> **Ejemplo ficticio.** Bórralo o reemplázalo por tu primer work slug. No describe un proyecto real.

# HANDOFF — example-feature

**Slug:** `example-feature` · **Actualizado:** sesión de ejemplo · **Sesión:** ejemplo
**Rama / base:** `main` · **Repos:** repositorio de ejemplo

## Objetivo

Dejar la búsqueda por texto lista para revisión y documentar la siguiente unidad.

## Estado actual

- **Git:** sin cambios pendientes en el ejemplo.
- **Documentación:** plan y handoff de ejemplo completos.
- **Decisiones:** búsqueda local, sin red; coincidencia por título y descripción.
- **Pendiente inmediato:** revisar si se resalta la coincidencia.
- **Pendiente de autorización:** ninguna; es un ejemplo.

### Estado por fase

| Fase | Estado | Nota |
|---|---|---|
| T1 · Campo de búsqueda | completada en el ejemplo | filtro local |
| T2 · Estado vacío | completada en el ejemplo | mensaje claro |

### Deudas con fecha

| Deuda | Revisión | Responsable | Criterio de cierre |
|---|---|---|---|
| Ninguna | — | — | — |

## Completado en esta sesión

- Campo de búsqueda con filtro local.
- Mensaje de estado vacío.
- Pruebas del filtro y del estado vacío.

**No se tocó:** datos reales, configuración de Git ni remotos.

## Verificación real

| Verificación | Resultado |
|---|---|
| Pruebas del filtro | los casos de ejemplo pasan |
| Revisión manual | la lista se filtra al escribir |
| Estado vacío | aparece solo sin coincidencias |

**No verificado:** rendimiento con muchas tareas.

## Problemas conocidos y bloqueos

1. El resaltado de coincidencias sigue siendo una decisión abierta.

## Siguiente acción

Decidir si se resalta la coincidencia en el título y, si se aprueba, implementarlo.

## Criterios de aceptación pendientes

- [x] Campo de búsqueda.
- [x] Estado vacío.
- [ ] Decidir el resaltado de coincidencias.

## Prompt de continuación

```text
Estamos en BUILD mode y continuamos el ejemplo `example-feature`.
Lee `AGENTS.md`, `docs/work/example-feature/PLAN.md` y `docs/work/example-feature/HANDOFF.md`.
Decide si se resalta la coincidencia y actualiza el handoff al terminar.
```

## Referencias

- Plan: `PLAN.md`
- Contexto: `docs/PROJECT_CONTEXT.md`
- Roadmap: `docs/ROADMAP.md`
- Reglas: `AGENTS.md`
