> **Ejemplo ficticio.** Bórralo o reemplázalo por tu primer work slug. No describe un proyecto real.

# PLAN — example-feature

**Slug:** `example-feature` · **Actualizado:** sesión de ejemplo
**Repos objetivo:** repositorio de ejemplo · **Rama/base:** `main`

## Objetivo

Permitir que una persona encuentre tareas por texto en un gestor de tareas de ejemplo.

## Alcance

**Dentro:**

- Campo de búsqueda en la lista de tareas.
- Coincidencia por título y descripción, sin distinguir mayúsculas.
- Resultados vacíos con un mensaje claro.

**Fuera:**

- Búsqueda semántica.
- Filtros por fecha o etiqueta.
- Persistencia del término entre sesiones.

## Contexto que hay que leer

- Reglas: `AGENTS.md`
- Contexto: `docs/PROJECT_CONTEXT.md`
- Roadmap: `docs/ROADMAP.md`
- Mapa de docs: `docs/README.md`

## Contexto técnico

Hechos del repositorio que el plan asume. Se verifican contra los archivos, no contra este texto.

| Hecho | Evidencia |
|---|---|
| La lista de tareas se renderiza en una sola página. | `docs/PROJECT_CONTEXT.md` |
| No hay backend; el estado vive en el cliente. | `docs/PROJECT_CONTEXT.md` |

## Decisiones cerradas

1. La búsqueda es local y no requiere red.
2. El término se normaliza a minúsculas antes de comparar.

## Decisiones abiertas

- ¿Se resalta la coincidencia en el título?

## Estado por fase

El avance y la siguiente acción viven en `HANDOFF.md`.

## Tareas

### T1 · Agregar el campo de búsqueda

- **Qué:** añadir un input y filtrar la lista en memoria.
- **Cómo:** estado local y una función de filtro.
- **Criterio de aceptación:** al escribir, la lista muestra solo las tareas que coinciden.
- **Verificación:** pruebas del filtro y revisión manual.

### T2 · Estado vacío

- **Qué:** mostrar un mensaje cuando no hay resultados.
- **Cómo:** renderizado condicional.
- **Criterio de aceptación:** el mensaje aparece solo con una búsqueda sin coincidencias.
- **Verificación:** prueba del estado vacío.

## Riesgos

| Riesgo | Impacto | Mitigación |
|---|---|---|
| El filtro se vuelve lento con muchas tareas | Mala experiencia | Medir con un conjunto de ejemplo y optimizar si hace falta |

## Registro

La bitácora de lo ejecutado vive en `CHANGELOG.md`. Este plan no acumula historia.
