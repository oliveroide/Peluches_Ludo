# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

HTML, CSS y JavaScript estáticos, sin framework (regla del proyecto en `CLAUDE.md`). Node solo para scripts de apoyo en `scripts/`. Máximo 3 dependencias npm, cada una justificada. Hosting en AWS, configurado por el usuario desde la consola; el servicio exacto y el dominio están por decidir.

## Users

Una mezcla de compradores, en este orden de peso:

1. **Personas que buscan un regalo** (cumpleaños, aniversarios, detalles).
2. **Coleccionistas y fans de peluches** que comparan modelos.
3. Madres y padres que compran para sus hijos.

La mayoría llega desde Instagram, en el celular.

## Product Purpose

Un catálogo web donde se ven los peluches de Peluches Ludo con su precio y desde donde se piden por mensaje directo de Instagram. Éxito: el visitante abre el DM (`https://ig.me/m/peluchesludo`) sabiendo qué peluche quiere y cuánto cuesta.

## Positioning

Precios muy bajos.

## Operating Context

El tráfico llega desde el perfil y las publicaciones de Instagram. La compra se acuerda y se cierra en el DM de Instagram, fuera del sitio.

## Capabilities and Constraints

- Sin carrito, pagos ni backend.
- La fuente de verdad de los productos es `data/productos.json`, con los campos `nombre`, `precio`, `imagen`, `url_instagram` y `revisar`.
- Los pedidos se hacen solo por `https://ig.me/m/peluchesludo`.
- El sitio está en español.
- Por decidir: el servicio de AWS, el dominio y la moneda o formato del precio.

## Brand Commitments

El nombre es "Peluches Ludo". Hay un logo y una identidad en uso en Instagram, pero todavía no están en el repositorio; se respetan cuando se agreguen.

## Evidence on Hand

El usuario tiene fotos de los productos, una lista de productos con precios y el logo, pero todavía no están en el repositorio (rutas por definir). No hay reseñas, testimonios ni cifras de ventas: no se inventan, igual que los productos y los precios.

## Product Principles

1. **El precio siempre a la vista.** Los precios bajos son la razón para comprar, así que no se esconden.
2. **Un solo camino de pedido.** Todo lleva al DM de Instagram; no hay rutas que compitan con él.
3. **Primero el celular que llega desde Instagram.** Carga rápida y que se entienda con el pulgar.
4. **Los datos en un solo lugar.** Cada producto se edita en `productos.json` y en ningún otro sitio.
