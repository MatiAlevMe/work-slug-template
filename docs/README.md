# docs/ — mapa

Documentación del proyecto `<PROJECT_NAME>`. Si un documento no encaja en una de estas carpetas, no se
escribe.

| Carpeta / archivo | Qué contiene | Se lee… | Se actualiza |
|---|---|---|---|
| `PROJECT_CONTEXT.md` | Qué es el proyecto, arquitectura y decisiones | siempre al empezar | cuando cambia la arquitectura o el contrato |
| `ROADMAP.md` | Fases y trabajo futuro no comprometido | al planificar | al cerrar una fase |
| `plans/` | Especificaciones aprobadas | al implementar | solo con autorización |
| `work/` | `<slug>/PLAN.md` y `<slug>/HANDOFF.md` obligatorios; el resto es opcional | solo la tarea activa | cada sesión |
| `templates/` | Plantillas de PLAN, HANDOFF, SESSION-START y REQ | al crear un documento | rara vez |
| `archive/` | Trabajo cerrado o diferido, congelado | solo para consultar antecedentes | nunca |
| `guides/` | Procedimientos de desarrollo, operación o uso | al ejecutar un procedimiento | cuando cambia el procedimiento |
| `requirements/` | Especificaciones de features en curso | al implementar un feature | mientras el feature está abierto |
| `knowledge/` | Lecciones, patrones, incidentes y referencia | al resolver un problema recurrente | cuando aparece una lección reutilizable |
| `domains/` | Mapas técnicos por dominio o módulo | al cambiar un dominio | en el mismo commit que el cambio |

## Naturaleza de los documentos

| Documento | Naturaleza | Se actualiza |
|---|---|---|
| `AGENTS.md` | Evergreen | reglas y comandos |
| `PROJECT_CONTEXT.md` | Evergreen | arquitectura o contrato |
| `ROADMAP.md` | Evergreen | fases, no progreso |
| `README.md` | Evergreen | uso o estructura; sin estado |
| `docs/README.md` | Evergreen | estructura |
| `templates/` | Evergreen | rara vez |
| `guides/` | Vivo | cuando cambia el procedimiento |
| `domains/` | Vivo | en el mismo commit que el cambio |
| `plans/` | Estable/aprobado | solo con autorización |
| `work/<slug>/PLAN.md` | Estable por slug (≤300 líneas) | cuando cambia el alcance |
| `work/<slug>/HANDOFF.md` | Estado (≤175 líneas) | cada sesión |
| `CHANGELOG.md` | Histórico | al publicar o cerrar |
| `BACKLOG.md` | Deuda diferida | al abrir o cerrar un ítem |
| `archive/` | Congelado | nunca |
| `requirements/` | Transitorio | mientras el feature está abierto |
| `knowledge/` | Memoria durable | cuando aparece una lección reutilizable |
| `work/example-feature/` | Ejemplo | se borra al adaptar |

Los documentos evergreen no llevan estado, fechas de progreso, hashes ni pendientes. El estado vive
en el handoff, lo histórico en `CHANGELOG.md` y lo cerrado en `archive/`.

## Ciclo de vida y enlaces

Un documento evergreen describe reglas, estructura o decisiones estables. Puede enlazar, pero solo a
rutas estables (`README.md`, `docs/README.md`, `plans/`, `guides/`). No enlaza a `work/<slug>/` ni a
`archive/` con rutas concretas: esas rutas viven solo en este mapa. Si un slug se archiva, se
actualiza una fila y ningún documento estable queda roto.

La deuda que sobrevive a un slug no se archiva con él: se registra en `BACKLOG.md`, en la raíz, con
responsable, fecha de revisión y criterio de cierre. Al cerrarse, se registra en `CHANGELOG.md` y se
retira del backlog.

## Reglas

1. **Nada nuevo en la raíz de `docs/`.** Solo `README.md`, `PROJECT_CONTEXT.md` y `ROADMAP.md`.
2. **Un slug activo por sesión.** Cada slug tiene `PLAN.md` y `HANDOFF.md`; al cerrarse se mueve a
   `archive/`, se registra en `CHANGELOG.md` y se actualiza este mapa. Los pendientes se absorben en el
   slug correspondiente o en `BACKLOG.md`.
3. **Las especificaciones aprobadas viven en `plans/`.** No se reescriben sin autorización.
4. **`archive/` se congela.** No se actualizan sus enlaces internos.
5. **Slugs ASCII.**
6. **Sin datos personales innecesarios.**
7. **Cada documento declara su naturaleza.**

## Recorridos típicos

| Quiero… | Ruta |
|---|---|
| Entender qué hace el proyecto | `PROJECT_CONTEXT.md` |
| Retomar el trabajo activo | `work/<slug>/HANDOFF.md` |
| Ver fases futuras | `ROADMAP.md` |
| Crear un documento nuevo | `templates/PLAN.md` o `templates/HANDOFF.md` |
| Consultar una especificación aprobada | `plans/` |
| Ver lo que ya se hizo | `../CHANGELOG.md` |

> El estado y la siguiente acción viven en el `HANDOFF.md` del slug activo. Este mapa solo describe
> qué existe, cuándo se lee y cuándo se actualiza.
