# AGENTS.md — <PROJECT_NAME>

Reglas para agentes que trabajan en este repositorio. **Este es el único archivo de instrucciones.**
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

El detalle está en `docs/README.md`.

## 4. Flujo de trabajo

1. **Planificar:** leer `PROJECT_CONTEXT.md`, `ROADMAP.md` y el `PLAN.md` del slug. No tocar archivos si
   la tarea es solo de planificación.
2. **Implementar:** una unidad verificable a la vez. Si el plan contradice el repositorio, detenerse y
   explicar; no improvisar arquitectura.
3. **Verificar:** ejecutar la verificación de la tarea y registrar el resultado real.
4. **Handoff:** reescribir `HANDOFF.md` con estado, verificación, siguiente acción única y prompt de
   continuación.

Una sesión trabaja sobre un solo slug activo. Si hay dos caminos razonables, usar una herramienta de
preguntas antes de elegir.

## 5. Git

- `main` es la rama permanente y la única que se publica.
- Ramas de trabajo: `docs/<slug>`, `feat/<slug>`, `fix/<slug>` o `chore/<slug>`, en ASCII.
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

## 7. Puertas de aprobación

Requieren autorización explícita:

- Publicar en el remoto o crear repositorios.
- Cambiar la visibilidad de un repositorio.
- Tocar repositorios externos.
- Cambiar dependencias o runtime.
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
