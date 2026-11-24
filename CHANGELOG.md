# Changelog

Registra cambios publicados o pendientes de publicación. No es un tablero de trabajo: el estado vive
en el handoff del slug activo y lo histórico en este archivo.

## Unreleased

### Added

- `BACKLOG.md` opcional para deuda, riesgos aceptados e ideas diferidas, con responsable, fecha de
  revisión y criterio de cierre.
- Nota de ciclo de vida y enlaces en `docs/README.md`: solo el mapa conoce rutas concretas de
  `work/<slug>/` y `archive/`.
- Plantilla inicial.

### Changed

- `AGENTS.md` agrega la regla de enlaces estables y el destino de la deuda que sobrevive a un slug.
- `AGENTS.md` documenta el cierre del slug, la siguiente acción con dueño `[manual]`/`[agente]` y los
  límites de `PLAN.md` y `HANDOFF.md`.
- `ADOPTING.md` agrega la guía para migrar un repositorio existente.
- Las plantillas de PLAN y HANDOFF reflejan los límites y el dueño de la siguiente acción.
- `README.md` y `ADOPTING.md` documentan el backlog opcional y su verificación.