# <PROJECT_NAME>

Plantilla de documentación y workflow para repositorios asistidos por agentes. Es agnóstica al stack:
no incluye código de aplicación, dependencias, CI ni datos privados.

## Qué incluye

- `AGENTS.md` como única fuente de instrucciones.
- Documentos base evergreen: `README.md`, `docs/PROJECT_CONTEXT.md`, `docs/ROADMAP.md` y
  `docs/README.md`.
- Unidad de trabajo `docs/work/<slug>/` con `PLAN.md` estable y `HANDOFF.md` reescrito cada sesión.
- Plantillas de PLAN, HANDOFF, SESSION-START y REQ.
- `docs/plans/` para especificaciones aprobadas y `docs/archive/` para trabajo congelado.
- Módulos opcionales: `docs/guides/`, `docs/requirements/`, `docs/knowledge/` y `docs/domains/`.
- Una guía de adopción, `ADOPTING.md`, y un slug de ejemplo ficticio.

## Cómo usarla

1. Crea un repositorio desde esta plantilla con **Use this template**, o copia el árbol sin importar
   el historial.
2. Sigue `ADOPTING.md` para reemplazar placeholders, configurar la identidad local y borrar lo que no
   uses.
3. Ejecuta el primer commit y publica solo con autorización.

## Estructura

```text
.
├── ADOPTING.md
├── AGENTS.md
├── CHANGELOG.md
├── LICENSE
├── README.md
└── docs/
    ├── README.md
    ├── PROJECT_CONTEXT.md
    ├── ROADMAP.md
    ├── archive/
    ├── plans/
    ├── templates/
    ├── work/example-feature/
    ├── guides/
    ├── requirements/
    ├── knowledge/
    └── domains/
```

## Principios de trabajo

- La documentación versionada es la fuente de verdad; el chat no es estado.
- `AGENTS.md` manda; los demás documentos apuntan a él.
- Evergreen, vivo, estable, estado, histórico y congelado no se mezclan.
- Cada tarea tiene un slug con plan estable y handoff reescrito.
- Se distingue lo verificado de lo asumido.
- Publicar, reescribir historial o tocar repos externos requiere autorización.

## Documentación

- [`AGENTS.md`](AGENTS.md): reglas y comandos.
- [`docs/README.md`](docs/README.md): mapa y naturaleza de los documentos.
- [`docs/PROJECT_CONTEXT.md`](docs/PROJECT_CONTEXT.md): contexto y decisiones estables.
- [`docs/ROADMAP.md`](docs/ROADMAP.md): fases y criterios de cierre.
- [`CHANGELOG.md`](CHANGELOG.md): cambios publicados o pendientes.
- [`ADOPTING.md`](ADOPTING.md): adaptación de la plantilla.

## Licencia

MIT. Ver [`LICENSE`](LICENSE). La licencia cubre el contenido genérico de la plantilla; no cubre los
datos, marcas o contenido que agregue cada proyecto.

## English summary

A stack-agnostic documentation and workflow template for agent-assisted repositories. It includes
AGENTS.md, evergreen project documents, work slugs with plans and handoffs, templates, and optional
modules. Use it as a GitHub template or copy the tree, then follow ADOPTING.md. The template is
MIT-licensed and does not include application code, CI, or private data.
