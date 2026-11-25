# Plan — Peluches Ludo

Se marca cada hito al terminarlo. El resumen general está en `docs/contexto.md`.

## Hitos

- [x] **0. Contexto**: `CLAUDE.md`, `PRODUCT.md`, `docs/PLAN.md` y `docs/contexto.md`.
- [ ] **1. Datos**: el esquema de `data/productos.json` (empieza como `[]`) y `scripts/validar-productos.mjs` (Node, sin dependencias).
- [ ] **2. Estructura del catálogo**: `index.html`, `css/` y `js/catalogo.js`, que leen el JSON y arman tarjetas con "Pedir por Instagram", más un estado vacío. Lo visual queda provisional.
- [ ] **3. Fundamentos**: `404.html`, `.gitignore`, `robots.txt` y metadatos.
- [ ] **4. Material real** *(necesita al usuario)*: fotos a `img/`, logo a `img/marca/` y la lista de precios cargada en `data/productos.json`.
- [ ] **5. Mundo visual** *(necesita al usuario)*: definir la dirección con Impeccable y escribir `DESIGN.md`.
- [ ] **6. Auditoría**: `/impeccable audit` y las correcciones que salgan.
- [ ] **7. Publicación en AWS**: `docs/AWS.md` con los pasos de consola (S3 + CloudFront) para el usuario.

## Preguntas pendientes

- ¿Dónde están las fotos, el logo y la lista de precios? Hay que copiarlos a la carpeta del proyecto (desbloquea los hitos 4 y 5).
- ¿En qué moneda y con qué formato se muestran los precios? (por ejemplo, `$199 MXN`)
- ¿Qué servicio de AWS y qué dominio se usarán? (hito 7)
