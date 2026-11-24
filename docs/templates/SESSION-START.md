# SESSION-START — prompts para abrir una sesión

## Retomar el trabajo activo

```text
Estamos en BUILD mode y continuamos `<PROJECT_NAME>` en `docs/work/<SLUG>/`.

Lee `AGENTS.md`, `docs/PROJECT_CONTEXT.md`, `docs/ROADMAP.md`, `docs/README.md`,
`docs/work/<SLUG>/PLAN.md` y `docs/work/<SLUG>/HANDOFF.md`. Revisa `git status`, `git branch -vv` y
los últimos commits.

No modifiques archivos todavía. Contrasta el handoff con los archivos y con Git. Si coincide, ejecuta
la siguiente acción única; si no, explica la diferencia antes de actuar.
```

## Planificar un slug nuevo

```text
Estamos en PLAN mode. Vamos a definir `docs/work/<SLUG>/PLAN.md` para `<PROJECT_NAME>`.

Lee `AGENTS.md`, `docs/PROJECT_CONTEXT.md`, `docs/ROADMAP.md` y `docs/README.md`.
Propón objetivo, alcance, fuera de alcance, decisiones abiertas, tareas verificables y riesgos.
No modifiques archivos todavía.
```

## Implementar una unidad

```text
Estamos en BUILD mode. Implementa una sola unidad verificable de `docs/work/<SLUG>/PLAN.md`.
Antes de empezar, lee el plan y el handoff. Al terminar, ejecuta la verificación real, actualiza el
handoff y no publiques sin autorización.
```

## Revisar un lote

```text
Estamos en PLAN mode. Revisa el lote de `<BRANCH>` contra `main`.
Contrasta la documentación con los archivos y con Git; clasifica hallazgos por severidad.
No modifiques archivos. Al terminar, pide aprobación explícita.
```

## Empezar un proyecto desde la plantilla

```text
Vamos a adaptar esta plantilla a `<PROJECT_NAME>`.
Sigue `ADOPTING.md`, reemplaza los placeholders y borra los módulos que no se usen.
No publiques ni cambies la configuración global de Git sin autorización.
```
