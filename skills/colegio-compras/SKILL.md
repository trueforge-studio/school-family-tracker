---
name: colegio-compras
description: Detecta qué hay que comprar o conseguir para el colegio de los hijos, lo confirma con el usuario ítem por ítem y recién entonces arma la lista o el prompt para un agente de compras. Usar cuando el usuario pregunte "¿qué hay que comprar?", "¿qué necesitamos para el colegio?", "lista de compras", "qué materiales faltan" o pida un prompt para el agente de compras.
---

# Compras del colegio

Carpeta: `colegio/` en la raíz del proyecto. Esta skill detecta y arma la lista; no compra nada. **Nunca entregues el prompt final sin confirmar antes con el usuario.**

## Paso 1: detectar
1. Lee `colegio/familia.md` y `colegio/estado.md`. Si la última sincronización tiene más de 2 días, ejecuta primero `colegio-actualizar` (o pregunta si hay apuro).
2. Lee `colegio/pendientes.md` y las semanas de `colegio/semanas/` de las próximas 2 semanas (una más si hay fin de semana largo o días sin clases). No leas `archivo/`.
3. Saca todo lo que el colegio pida **comprar, conseguir o mandar**: materiales de trabajos y maquetas, útiles, libros de plan lector, ingredientes, ropa pedida, kits, etc.
4. Si el usuario pasó una lista suya, úsala como base.

## Paso 2: confirmar con el usuario (obligatorio)
Muestra los candidatos agrupados por hijo y fecha, en una lista numerada y corta, con lo que el colegio pidió **textual** (medidas, material, cantidad) y el ID de Notasnet. Cuando el colegio dice "o similar" o da una alternativa, dilo. Indica qué cosas son habituales (agua, gorro, bloqueador, toallitas) y no las listes salvo que el usuario lo pida.

Pregunta, para cada ítem, cuál de estos es:
- **Comprar** (y si cambia algo: tamaño, marca, material, cantidad).
- **Ya lo tenemos.**
- **No aplica / no se compra** (por ejemplo, si no existe el material pedido y se usa otra cosa).
- **Opcional / después.**

Espera su respuesta. Si responde con detalles ("la pelota no es de plumavit, ya la compré"), ajusta y no vuelvas a preguntar eso. Si quedan dudas sobre un ítem, pregunta solo por ese. No supongas una tienda y no inventes cantidades ni marcas.

## Paso 3: entregar la lista final
Solo con lo que el usuario marcó **Comprar**:
- Tabla: **Producto | Cantidad | Para quién | Para qué | Fecha límite**, ordenada por fecha (lo urgente primero).
- Un bloque de texto listo para pegar al agente de compras, con los productos tal como el usuario los confirmó, la fecha de entrega y la instrucción de **no comprar nada fuera de esta lista** y de avisar si algo no se encuentra, en vez de reemplazarlo.
- Una línea con lo que quedó fuera (ya lo tienen, no aplica, después), para que se vea qué se descartó.

## Memoria de lo habitual
Si el usuario te dice que algo es habitual o que no lo listes nunca (por ejemplo "el agua y el bloqueador no los listes"), anótalo en `colegio/familia.md`, sección "Preferencias", para no volver a preguntarlo.
