# <PROJECT_NAME> — contexto

> Documento de entrada. El estado y la siguiente acción viven en `work/<slug>/HANDOFF.md`.

## Qué es

`<PROJECT_NAME>` es `<PROJECT_PURPOSE>`.

## Stack y arquitectura

- Stack: `<STACK>`.
- Entradas principales: describir qué recibe el proyecto.
- Salidas principales: describir qué produce.
- Componentes: describir los bloques principales.

Ajustar esta sección al proyecto real.

## Módulos o dominios

| Módulo / dominio | Responsabilidad |
|---|---|
| Dominio A | Responsabilidad del dominio A. |
| Dominio B | Responsabilidad del dominio B. |

Si el proyecto no tiene dominios, borrar la tabla.

## Decisiones vigentes

1. **Fuente de verdad.** El código y los documentos versionados son la fuente; el chat no es estado.
2. **Documentación separada del contenido.** Las reglas viven en `AGENTS.md`; las propuestas en
   `docs/work/`; las especificaciones aprobadas en `docs/plans/`.
3. **Unidad de trabajo.** Cada tarea tiene un slug con plan estable y handoff reescrito.
4. **Privacidad.** Los datos sensibles viven fuera de Git.
5. **Agnóstico al stack.** La plantilla no impone lenguaje, framework ni CI.

## Flujo de trabajo

1. Planificar.
2. Implementar una unidad verificable.
3. Verificar y registrar el resultado real.
4. Reescribir el handoff.

## Dónde vive el estado

| Qué | Dónde |
|---|---|
| Estado, verificación y siguiente acción | `docs/work/<slug>/HANDOFF.md` |
| Hallazgos y decisiones del slug | `docs/work/<slug>/PLAN.md` |
| Qué se hizo | `CHANGELOG.md` |
| Fases y orden del trabajo | `docs/ROADMAP.md` |
| Trabajo cerrado | `docs/archive/` |

## Criterios de una iteración confiable

- Los cambios son verificables y están documentados.
- No se tocaron datos sensibles sin autorización.
- Los enlaces relativos resuelven.
- Las tablas Markdown son consistentes.
- El handoff distingue lo verificado de lo asumido.
- La siguiente acción es única y retomable en una sesión nueva.

Este documento describe lo estable. No lleva estado, fechas de progreso ni pendientes.
