# AGENTS.md — <PROJECT_NAME>

Reglas para agentes que trabajan en este repositorio. **Este es el único archivo de instrucciones.**
Si encuentras otro (reglas de IDE, notas sueltas), está obsoleto: manda este.
Es un documento evergreen: no lleva estado, fechas de progreso, hashes ni pendientes. El estado vive
en el handoff del slug activo; lo histórico, en `CHANGELOG.md`; lo cerrado, en `docs/archive/`.

## 0. Qué es este repositorio

`<PROJECT_NAME>` es `<PROJECT_PURPOSE>`.

Stack: `<STACK>`.

No inventar arquitectura, datos, métricas ni resultados. Si falta contexto, detenerse y preguntar.

## 1. Reglas no negociables

| Regla | Detalle |
|---|---|
| **Fuente de verdad** | El código y los documentos versionados son la fuente; el chat no es estado. |
| **No inventar datos** | No completar hechos, métricas, fechas, resultados ni tecnologías sin evidencia. |
| **Commits atómicos** | Un cambio verificable por commit. |
| **Push con aprobación** | Publicar, crear repos, cambiar visibilidad o tocar repos externos requiere autorización. |
| **Sin secretos** | No commitear `.env`, credenciales, tokens, claves ni datos sensibles. |
| **Archivos ≤ 1000 líneas** | Si un documento o script supera el límite, se justifica y se divide por responsabilidad. |
| **Verificación real** | Distinguir lo ejecutado de lo asumido; no inventar resultados. |
| **Preservar trabajo del usuario** | Investigar antes de borrar o sobrescribir archivos desconocidos. |
| **Documentación actualizada** | El cambio y su documentación van en el mismo commit cuando corresponda. |

## 2. Stack y comandos

| Componente | Comando |
|---|---|
| Instalar | `<INSTALL_COMMAND>` |
| Desarrollo | `<DEV_COMMAND>` |
| Pruebas | `<TEST_COMMAND>` |
| Build | `<BUILD_COMMAND>` |

Borrar las filas que no apliquen. Si un comando no existe, no inventarlo.

## 3. Documentación

```text
AGENTS.md              reglas para agentes
CHANGELOG.md           cambios publicados o pendientes
README.md              entrada humana
docs/
├── README.md          mapa y naturaleza de los documentos
├── PROJECT_CONTEXT.md qué es y decisiones estables
├── ROADMAP.md         fases y criterios de cierre
├── plans/             especificaciones aprobadas
├── work/<slug>/       PLAN.md + HANDOFF.md del trabajo activo
├── templates/         plantillas de documentos
├── archive/           trabajo cerrado y congelado
├── guides/            módulo opcional
├── requirements/      módulo opcional
├── knowledge/         módulo opcional
└── domains/           módulo opcional
```

Reglas:

1. Nada nuevo en la raíz de `docs/` salvo `README.md`, `PROJECT_CONTEXT.md` y `ROADMAP.md`.
2. `PLAN.md` y `HANDOFF.md` son los dos únicos archivos obligatorios de cada slug.
3. Las especificaciones aprobadas viven en `docs/plans/`.
4. `docs/archive/` está congelado.
5. Slugs ASCII.
6. Sin datos personales innecesarios.
7. Los hallazgos van al `PLAN.md` del slug; si no cambian alcance, criterio o riesgo, no se
   archivan.
8. El `CHANGELOG.md` registra cambios publicados, no trabajo en curso.

El detalle está en `docs/README.md`.

## 4. Flujo de trabajo

**Arranque de sesión:** leer este archivo y `docs/README.md`. Si retomas trabajo en curso, abre
`docs/work/<slug>/`, lee `PLAN.md` y `HANDOFF.md` y contrástalos con `git status` y `git log` antes
de actuar. El handoff manda sobre la memoria de la conversación. Los prompts de
[`docs/templates/SESSION-START.md`](docs/templates/SESSION-START.md) abren la sesión en modo plan o
build; respetar el modo declarado.

1. **Planificar:** leer `PROJECT_CONTEXT.md`, `ROADMAP.md` y el `PLAN.md` del slug. No tocar archivos
   si la tarea es solo de planificación. Las decisiones de diseño —alcance, arquitectura,
   estrategia— se resuelven antes de implementar.
2. **Implementar:** una unidad verificable a la vez. Si el plan contradice el repositorio, detenerse
   y explicar; no improvisar arquitectura.
3. **Verificar:** ejecutar la verificación de la tarea y registrar el resultado real. Revisar el diff
   en modo lectura y distinguir defectos confirmados de sospechas. Si el cambio es delicado,
   verificar en una sesión aparte. La verificación es por entorno: lo validado en un sistema
   operativo no se presume validado en otro, y las comparaciones binarias o raster se hacen contra una
   referencia del mismo entorno. Si hace falta un entorno que no está disponible, se registra como
   pendiente manual con su alcance y no se marca como hecho.
4. **Handoff:** reescribir `HANDOFF.md` con estado, verificación real, siguiente acción única y prompt
   de continuación. La siguiente acción es una unidad ejecutable, no una fecha: las obligaciones con
   fecha viven en «Deudas con fecha». El prompt referencia el handoff y no duplica su estado.

Una sesión trabaja sobre un solo slug activo. Si la tarea toca otro slug o repositorio, declarar el
slug primario y registrar el resto como dependencia o bloqueo; no mantener dos handoffs en paralelo.
Si el trabajo se alarga, se repiten pasos o el contexto se degrada, cerrar el handoff y abrir una
sesión nueva. Al cortar, pegar el prompt de continuación en el mensaje final.

### Decisiones y preguntas al usuario

Cuando una decisión tenga dos o más caminos razonables (alcance, arquitectura, prioridad, datos),
usar la herramienta de preguntas del entorno —`question` en OpenCode— antes de elegir:

- una pregunta por decisión, con opciones cortas y una `description` que explique qué implica cada
  una;
- la opción recomendada primero, con «(Recommended)» al final de la etiqueta;
- si la decisión bloquea una escritura, un borrado o una publicación, detenerse hasta la respuesta.

No usarla para confirmaciones triviales ni para datos que ya están en el repositorio o en el
handoff.

## 5. Git

- `main` es la rama permanente y la única que se publica.
- El trabajo va en una rama local; `main` solo recibe integraciones verificadas.
- Ramas de trabajo: `docs/<slug>`, `feat/<slug>`, `fix/<slug>` o `chore/<slug>`, en ASCII.
- Al cerrar, integrar la rama en `main` local y ejecutar la verificación final en la misma sesión.
  No acumular ramas validadas sin integrar; integrar en local no equivale a publicar.
- Si dos agentes escriben en paralelo, cada uno en su worktree; nunca dos agentes en el mismo
  directorio.
- Commits: `tipo(scope): descripción` en español, atómicos.
- Identidad local: configurar `user.name` y `user.email` en el repositorio; no cambiar la global.
- Push: solo con aprobación explícita.
- Historial: no reescribir, hacer force-push ni cambiar la identidad sin backup verificado y
  autorización explícita.

## 6. Privacidad y datos

- Los secretos viven fuera de Git.
- `<SENSITIVE_DATA>` no se commitea, no se pega en issues ni se publica.
- Un repositorio privado no es control de acceso: si se publica, es legible.
- Git conserva historial aunque un archivo se elimine del árbol actual.
- Si una alerta o riesgo no se puede cerrar, se documenta con responsable, fecha de revisión y
  límite operativo; no se extiende por omisión.

## 7. Puertas de aprobación

Requieren autorización explícita:

- Publicar en el remoto o crear repositorios.
- Cambiar la visibilidad de un repositorio.
- Tocar repositorios externos.
- Cambiar dependencias, runtime o configuración global del entorno.
- Ejecutar migraciones u operaciones destructivas sobre datos.
- Borrar datos o archivos del usuario.
- Reescribir historial o hacer force-push.

## 8. Índice mínimo

| Documento | Para qué |
|---|---|
| `docs/PROJECT_CONTEXT.md` | contexto y decisiones estables |
| `docs/ROADMAP.md` | fases y criterios |
| `docs/work/<slug>/HANDOFF.md` | estado real y siguiente acción |
| `docs/README.md` | mapa de la documentación |
| `CHANGELOG.md` | qué se hizo |

Este archivo no registra estado. No agregar fechas de progreso, hashes ni pendientes.
