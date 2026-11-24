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
git config --local user.email "<GIT_USER_EMAIL>"
git config --local --get user.name
git config --local --get user.email
```

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
| `<GIT_USER_EMAIL>` | Email o noreply para los commits locales. |
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

## 7. Verificar antes del primer commit

- [ ] No quedan placeholders sin reemplazar.
- [ ] Los enlaces relativos resuelven.
- [ ] Las tablas Markdown son consistentes.
- [ ] No hay datos personales, secretos ni rutas absolutas.
- [ ] `AGENTS.md` es la única fuente de instrucciones.
- [ ] Los documentos evergreen no enlazan rutas concretas de `work/<slug>/` ni `archive/`.
- [ ] `BACKLOG.md` está borrado o sin placeholders ni filas de ejemplo.
- [ ] La identidad local está configurada y la global no cambió.
- [ ] El repositorio no tiene remotos heredados.

## 8. Primer commit y publicación

```bash
git add .
git commit -m "docs(project): adaptar plantilla"
```

Publica solo con autorización explícita. Si el repositorio será una plantilla, audítalo y marca la
opción de template después, no antes.

## 9. Mantenimiento

- La plantilla no se sincroniza automáticamente.
- Las mejoras se aplican manualmente a cada repositorio.
- Si adoptas una convención nueva, actualiza `AGENTS.md`, `docs/README.md` y este archivo en el mismo
  cambio.
