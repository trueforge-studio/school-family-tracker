---
name: colegio-semana
description: Resume qué hay hoy, mañana, esta semana o la próxima en el colegio (tareas, pruebas, materiales para enviar, salidas, días sin clases) para uno o todos los hijos. Usar cuando el usuario pregunte "¿qué hay mañana?", "¿qué hay la próxima semana?", "¿qué tareas tienen?", "¿qué tengo que mandar mañana?", "¿qué tiene <hijo>?".
---

# Resumen del colegio

Carpeta: `colegio/` en la raíz del proyecto.

## Pasos
1. Lee `colegio/familia.md` y `colegio/estado.md`. Si la última sincronización tiene más de 2 días, ejecuta primero la skill `colegio-actualizar`, o pregunta si actualizar cuando el usuario tenga apuro.
2. Lee `colegio/pendientes.md` y el archivo de la semana que pidió: `colegio/semanas/AAAA-MM-DD.md`, con el lunes de esa semana. "Próxima semana" es el lunes siguiente a hoy; si hoy es sábado o domingo, es la semana que empieza mañana.
3. Si pregunta por un solo hijo, usa solo su sección y las filas con su etiqueta y las generales. No leas `archivo/`, salvo que pregunte por algo que ya pasó.
4. Si el usuario pasó una foto de la agenda o del panel en papel, aplica primero la skill `colegio-papel`.

## Formato de respuesta (en español, conciso)
- Primera línea: la idea general (días sin clases, salidas anticipadas).
- **Lo urgente primero:** lo de hoy o mañana, o lo que hay que enviar, con fecha.
- Luego, día a día, o una tabla Día | hijos... | Apoderados.
- "Tareas y cosas para la casa": lo que hay que preparar, comprar o estudiar, incluido lo que vence la semana siguiente y conviene adelantar (fines de semana largos).
- "Por confirmar": las ⚠️ de pendientes.md.
- No inventes. Si una fecha viene solo de la agenda o solo del papel, dilo.
