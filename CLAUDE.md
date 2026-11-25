# CLAUDE.md — Escritorio

Lanzador personal que une las apps del propietario. Proyecto **independiente**: no usa la Bitácora ni los tests de SHAAH. Historial en `CHANGELOG.md`.

## Estructura
- `index.html` (con CSP estricta: nada de scripts inline), `app.css`, `app.js`, `evento.js`, `sw.js` (service worker propio, red primero), `manifest.webmanifest`, iconos.
- `vendor/supabase-2.118.0.js`: login de Google (misma sesión que SHAAH y Cocina; mismo origen `trypartylol-max.github.io`).
- Lista de apps: `BUILTIN` en `app.js`. Cada app vive en su propio repo; aquí solo va el enlace.

## Datos
- API de Apps Script (constantes `API` y `PRIV` en `app.js`), atada a la hoja Plata26 del propietario. El código de esa API no está en este repo.
- Credencial: clave del dispositivo en localStorage (`esc-key`) o JWT de la sesión de Supabase.

## Publicar
- GitHub Pages sirve `main`. El propietario revisa antes: no hagas merge de un cambio visible sin su "publica".
- Al cambiar archivos: actualiza `?v=` en `index.html` y sube `CACHE` en `sw.js`.
- El diseño se juzga a la resolución de su monitor (~2560 px).
