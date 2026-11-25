---
name: colegio-papel
description: Ingresa a colegio/ lo que viene en papel (foto o texto de la agenda, el panel de contenidos y deberes o una comunicación escrita en la libreta). Usar cuando el usuario mande una foto de la agenda, del panel o de una comunicación del colegio, o dicte algo que dijo el profesor.
---

# Ingresar agenda o panel en papel

Carpeta: `colegio/` en la raíz del proyecto. Esta información no está en Notasnet; el papel es la única fuente.

## Pasos
1. Transcribe la imagen con cuidado. Suele venir rotada: las fechas, los materiales y las cantidades tienen que quedar exactos. Si algo no se lee, márcalo con "(ilegible)" y pregunta; no lo adivines.
2. Identifica de qué hijo es. `colegio/familia.md` dice quién tiene agenda en papel; si hay más de uno o no es claro, pregunta.
3. Separa en:
   - **Deberes con fecha:** materiales para enviar, evaluaciones, salidas, días sin clases.
   - **Contenidos por asignatura:** van resumidos en una línea por asignatura.
4. Para cada semana que aparezca, edita `colegio/semanas/AAAA-MM-DD.md` (el lunes de esa semana; si no existe, créalo con `plantillas/semana.md`). Pon los deberes como viñetas con fecha y la fuente "(papel)". Los contenidos van bajo "**Contenidos de la semana**".
5. Agrega los deberes con fecha a `colegio/pendientes.md`, con la etiqueta del hijo y la fuente (papel).
6. Cruza con lo que ya está en pendientes y en la semana, que viene de Notasnet. Si hay fechas distintas, marca ⚠️ en las dos partes y avísalo al usuario.
7. Anota en `colegio/estado.md`, sección "Papel", qué se ingresó y la fecha.

## Respuesta al usuario
Lo más urgente primero (sobre todo lo que hay que enviar mañana), después lo nuevo por día y las discrepancias con Notasnet.
