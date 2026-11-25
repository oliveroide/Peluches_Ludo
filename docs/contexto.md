# Contexto del proyecto: Peluches Ludo

> Este archivo resume el estado del proyecto. Sirve para retomarlo en otra sesión (o en otra máquina) sin perder el hilo.
> Última actualización: 2026-11-24.

## Objetivo

Hacer un **catálogo web** de Peluches Ludo donde la gente vea los peluches con su precio y los pida por **mensaje directo de Instagram** (`https://ig.me/m/peluchesludo`). No hay carrito, pagos ni backend.

También es un **proyecto de aprendizaje**: cada archivo y cada decisión se explican antes de crearlos.

## Decisiones tomadas

| Tema | Decisión | Origen |
|---|---|---|
| Plataforma | Web (pensada primero para el celular) | Respuesta del usuario |
| Stack | HTML/CSS/JS sin framework; Node solo en `scripts/`; máximo 3 dependencias npm, cada una justificada | CLAUDE.md |
| Datos | La fuente de verdad es `data/productos.json` (campos `nombre`, `precio`, `imagen`, `url_instagram`, `revisar`) | CLAUDE.md |
| Pedidos | Solo por `https://ig.me/m/peluchesludo` | CLAUDE.md |
| Clientes | Mezcla; predominan **personas que buscan un regalo** y **coleccionistas/fans**, que llegan desde Instagram en el celular; también padres | Respuesta del usuario |
| Diferencia frente a otras tiendas | **Precios muy bajos** | Respuesta del usuario |
| Diseño | Con la skill Impeccable; correr `/impeccable audit` antes de cerrar cada hito visual | CLAUDE.md |
| Hosting | AWS. El usuario lo configura por consola; Claude no ejecuta comandos de AWS ni lee `~/.aws/` | CLAUDE.md |
| Git | Sin `commit`/`push`/comandos destructivos a menos que el usuario lo pida | CLAUDE.md |
| Ritmo | En esta sesión se avanza hito tras hito sin esperar "siguiente". Lo que necesite al usuario se anota como pregunta pendiente y se salta al siguiente hito independiente | Instrucción del usuario |

## Material que existe (fuera del repo por ahora)

- Fotos de los productos
- Lista de productos y precios
- Logo e identidad de la marca

No se inventan productos, precios, reseñas ni testimonios. Mientras el material real no esté en el repo, el catálogo usa un estado vacío.

## Qué ya está hecho

- [x] Interview de producto (`/impeccable init`): respuestas recogidas (tabla de arriba).
- [x] Plan aprobado.
- [x] Este archivo (`docs/contexto.md`).
- [x] **Hito 0 terminado**: `CLAUDE.md`, `PRODUCT.md` y `docs/PLAN.md` creados.

## Qué falta

### Hito 0: contexto (hecho)
1. `CLAUDE.md`: las reglas del proyecto, copiadas tal cual del texto que pegó el usuario.
2. `PRODUCT.md`: el registro de producto de Impeccable, con los hechos confirmados de arriba y sin decisiones visuales.
3. `docs/PLAN.md`: la lista de hitos con casillas y la sección "Preguntas pendientes".

### Hitos que se pueden hacer sin supervisión
4. **Datos**: el esquema de `data/productos.json` (arranca como `[]`) y `scripts/validar-productos.mjs` (Node puro, sin dependencias), que revisa campos, precios y rutas de imagen.
5. **Estructura del catálogo**: `index.html` + `css/` + `js/catalogo.js`, que leen el JSON y arman las tarjetas con el botón "Pedir por Instagram", más un estado vacío. Lo visual es neutro y provisional.
6. **Fundamentos**: `404.html`, `.gitignore`, `robots.txt` y metadatos básicos.
7. **AWS**: `docs/AWS.md` con los pasos de consola (S3 + CloudFront) para que el usuario los siga.
8. **Auditoría**: `/impeccable audit` sobre lo construido, y corregir lo que salga.

### Hitos bloqueados: necesitan al usuario
- **Material real**: copiar las fotos a `img/`, el logo a `img/marca/`, y la lista de precios para llenar `data/productos.json`.
- **Mundo visual (DESIGN.md)**: necesita el logo y la identidad actuales de Instagram, y las decisiones de dirección visual.
- **Publicación**: qué servicio de AWS se usa y si habrá dominio propio.

## Siguientes pasos concretos

1. ~~Hito 0~~ (hecho).
2. Seguir con los hitos 4 a 8 en orden, anotando cada duda en `docs/PLAN.md` → "Preguntas pendientes".
3. **Para el usuario**: pasar las fotos, el logo y la lista de precios a la carpeta del proyecto, para desbloquear los datos reales y el diseño visual.

## Plan completo (aprobado)

El plan original se guardó en `~/.claude/plans/`. Esta es la copia:

### Contexto
La carpeta `Proyectos/` estaba vacía. El usuario corrió `/impeccable init` y pegó las reglas del proyecto. El Hito 0 deja escrito el contexto durable, para que el diseño y el código posteriores partan de hechos confirmados. En ese hito no se escribe código ni diseño visual.

### Archivos del Hito 0 (en orden)
1. **`CLAUDE.md`**: el texto pegado tal cual. Es el archivo de reglas que Claude Code carga solo en cada sesión.
2. **`PRODUCT.md`** (schema 1 de Impeccable), con estas secciones:
   - `Platform`: `web`
   - `Stack`: HTML/CSS/JS estático, Node solo en `scripts/`, máximo 3 dependencias, AWS (servicio por decidir)
   - `Users`: personas que buscan un regalo y coleccionistas/fans, desde Instagram en el celular; también padres
   - `Product Purpose`: ver los peluches con su precio y pedirlos por DM. Éxito: el visitante abre el DM sabiendo qué peluche quiere
   - `Positioning`: precios muy bajos
   - `Operating Context`: el tráfico llega desde Instagram; la compra se cierra en el DM
   - `Capabilities and Constraints`: sin carrito, pagos ni backend; `productos.json` como fuente de verdad; sitio en español
   - `Brand Commitments`: el nombre "Peluches Ludo"; el logo e identidad se usarán cuando estén en el repo
   - `Evidence on Hand`: hay fotos, precios y logo, pero fuera del repo; no inventar nada
   - `Product Principles`: el precio siempre visible; un solo camino de pedido (DM); primero el celular; los datos en un solo lugar
3. **`docs/PLAN.md`**: los hitos con casillas y las preguntas pendientes.

No hay `.impeccable/config.json` (no hay generación de imágenes, así que no hay que elegir entre comp-first y code-first) ni live mode (todavía no hay servidor de desarrollo).

### Verificación
- `ls` muestra los archivos creados.
- `impeccable context` deja de reportar `NO_PRODUCT_MD`.
- PRODUCT.md coincide con las respuestas confirmadas: nada inventado, y lo abierto queda marcado como abierto.
- `node scripts/validar-productos.mjs` pasa con el JSON vacío.
- `index.html` se revisa con `impeccable shot` en tamaño de celular y de escritorio.
- Al final: un resumen y la lista de archivos que conviene commitear (`CLAUDE.md`, `PRODUCT.md`, `docs/`, el código).
