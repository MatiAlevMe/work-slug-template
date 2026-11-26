# ADOPTING — cómo usar esta plantilla

Esta plantilla es un punto de partida. No se sincroniza automáticamente con los repositorios creados
a partir de ella.

## 1. Crear el repositorio

- Usa **Use this template** en GitHub, o copia el árbol a un directorio nuevo.
- No importes el historial de la plantilla ni de otro repositorio.
- Si copias el árbol, inicializa un repositorio nuevo y revisa que no arrastres `.git` ni archivos
  ocultos.

## 2. Configurar la identidad local

No cambies la configuración global de Git. En el repositorio nuevo:

```bash
git config --local user.name "<GIT_USER_NAME>"
git config --local user.email "<GITHUB_NOREPLY>"
git config --local --get user.name
git config --local --get user.email
```

Política de identidad:

- **Repos públicos:** commits con `<GITHUB_NOREPLY>`. No commitear el email personal ni un `.mailmap`
  con emails personales.
- **Repos privados:** `<GITHUB_NOREPLY>` por defecto; el email personal solo si el proyecto lo necesita
  y el repositorio seguirá privado.
- Verificar `git config --local --get user.email` antes del primer commit.
- Antes de cambiar un repositorio de privado a público, revisar autores, committers y blobs del
  historial. Un repositorio privado no es control de acceso: Git conserva lo que se publicó.

## 3. Reemplazar placeholders

| Placeholder | Qué reemplazar |
|---|---|
| `<PROJECT_NAME>` | Nombre corto del proyecto. |
| `<PROJECT_PURPOSE>` | Una frase sobre qué hace y para quién. |
| `<OWNER>` | Persona o equipo responsable. |
| `<REPO_URL>` | URL pública o interna del repositorio. |
| `<DEFAULT_BRANCH>` | Rama principal; por defecto `main`. |
| `<STACK>` | Tecnologías principales. |
| `<INSTALL_COMMAND>` | Comando para instalar dependencias. |
| `<DEV_COMMAND>` | Comando para desarrollo local. |
| `<TEST_COMMAND>` | Comando para pruebas. |
| `<BUILD_COMMAND>` | Comando para build o empaquetado. |
| `<SENSITIVE_DATA>` | Datos que el proyecto no debe publicar. |
| `<GIT_USER_NAME>` | Nombre para los commits locales. |
| `<GITHUB_NOREPLY>` | Noreply de GitHub con forma `id+usuario@users.noreply.github.com`; obligatorio en repos públicos. |
| `<SLUG>` | Identificador ASCII del work slug. |
| `<DATE>` | Fecha de la sesión o del documento. |
| `<BRANCH>` | Rama de trabajo. |
| `<NEXT_ACTION>` | Siguiente unidad de trabajo. |
| `<FEATURE_ID>` | Identificador de un requirement. |
| `<LIMIT>` | Límite operativo o criterio de un riesgo aceptado. |
| `<REASON>` | Motivo para diferir una idea. |

Reemplaza o elimina cada placeholder. No dejes placeholders como texto final en el proyecto adaptado.

## 4. Completar el proyecto

- Ajusta `AGENTS.md`: stack, comandos y puertas de aprobación.
- Si adoptas trunk-based en lugar de ramas locales, ajusta `AGENTS.md` §5; el resto del flujo no
  cambia.
- Ajusta `README.md`, `docs/PROJECT_CONTEXT.md` y `docs/ROADMAP.md`.
- Define qué datos son sensibles y dónde viven fuera de Git.
- Borra las filas de comandos que no apliquen.
- Usa `BACKLOG.md` solo si acumulas deuda o riesgos aceptados; si no, borra el archivo. Si lo usas,
  reemplaza o elimina las filas de ejemplo y los placeholders `<LIMIT>` y `<REASON>`.

## 5. Elegir módulos opcionales

Conserva solo los módulos que uses:

- `docs/guides/`
- `docs/requirements/`
- `docs/knowledge/`
- `docs/domains/`

Cada README explica cuándo usarlo y cómo borrarlo. El núcleo no depende de ellos.

## 6. Reemplazar el ejemplo

- Borra o reemplaza `docs/work/example-feature/`.
- Crea el primer work slug real con `docs/templates/PLAN.md` y `docs/templates/HANDOFF.md`.
- Si usas requirements, copia `docs/templates/REQ.md` a `docs/requirements/`.

## 7. Migrar un repositorio existente

No copies la plantilla completa. Adapta lo que falta y conserva lo específico del proyecto.

1. Lee `AGENTS.md`, `docs/README.md` y el handoff activo del repositorio.
2. Saca el estado de `AGENTS.md`: debe vivir en el handoff del slug.
3. Reemplaza los enlaces a `work/<slug>/` por referencias al mapa; las rutas concretas viven solo en
   `docs/README.md`.
4. Agrega las reglas de interacción y flujo que falten: Question tool, arranque de sesión, worktrees,
   verificación por entorno, cierre de slug, siguiente acción con dueño y límites de tamaño.
5. Conserva las secciones específicas: stack, comandos, privacidad, contratos y reglas de negocio.
6. Crea un slug corto con `PLAN.md` y `HANDOFF.md` que registre la migración y su verificación.
7. Verifica enlaces, tablas, límites de líneas y `git diff --check`; publica solo con autorización.

Una migración por repositorio y por sesión. No mezcles varios repos en un mismo slug.

## 8. Verificar antes del primer commit

- [ ] No quedan placeholders sin reemplazar.
- [ ] Los enlaces relativos resuelven.
- [ ] Las tablas Markdown son consistentes.
- [ ] No hay datos personales, secretos ni rutas absolutas.
- [ ] `AGENTS.md` es la única fuente de instrucciones.
- [ ] `AGENTS.md` no contiene estado; vive en el handoff del slug.
- [ ] Los documentos evergreen no enlazan rutas concretas de `work/<slug>/` ni `archive/`.
- [ ] `PLAN.md` ≤300 líneas y `HANDOFF.md` ≤175.
- [ ] La siguiente acción del handoff separa `[manual: usuario]` y `[agente]`.
- [ ] `BACKLOG.md` está borrado o sin placeholders ni filas de ejemplo.
- [ ] La identidad local está configurada con `<GITHUB_NOREPLY>` y la global no cambió.
- [ ] Los archivos actuales no contienen el email personal; `LICENSE` solo lleva el titular, sin email.
- [ ] No hay `.mailmap` con emails personales en un repositorio público.
- [ ] Si el repositorio era privado y se hizo público, se revisó el historial.
- [ ] El repositorio no tiene remotos heredados.

## 9. Primer commit y publicación

```bash
git add .
git commit -m "docs(project): adaptar plantilla"
```

Publica solo con autorización explícita. Si el repositorio será una plantilla, audítalo y marca la
opción de template después, no antes.

## 10. Mantenimiento

- La plantilla no se sincroniza automáticamente.
- Las mejoras se aplican manualmente a cada repositorio.
- Si adoptas una convención nueva, actualiza `AGENTS.md`, `docs/README.md` y este archivo en el mismo
  cambio.
