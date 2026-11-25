---
name: colegio-iniciar
description: Configura por primera vez el seguimiento escolar de una familia: detecta los hijos en Notasnet, crea la carpeta colegio/ con sus archivos y hace la primera sincronización. Usar cuando colegio/familia.md no exista, o cuando el usuario diga "inicializa", "configura esto para mis hijos" o "empezar".
---

# Inicializar el seguimiento escolar

Carpeta de datos: `colegio/` en la raíz del proyecto. Las plantillas están en `plantillas/`.

## Pasos
1. Si `colegio/familia.md` ya existe, avisa y pregunta si quiere reiniciar (no borres nada sin su confirmación explícita).
2. Verifica que las herramientas `notasnet_*` estén disponibles (si tu agente las carga bajo demanda, búscalas por "notasnet"). Si no lo están, explícale que falta instalar el MCP (ver README, sección "Requisitos") y detente. Carga `notasnet_session_status`; si no hay sesión, pídele que inicie sesión él mismo. Nunca escribas su contraseña.
3. Descubre a los hijos con `notasnet_list_students` (y `notasnet_get_student_info` si hace falta). Muéstrale lo encontrado (nombre, curso, ID de alumno) y confirma que sean los correctos.
4. Pregúntale, de una sola vez:
   - una **etiqueta corta** para cada hijo (por ejemplo la inicial; sirve para marcar [A], [C] en los pendientes);
   - si alguno tiene **agenda o panel en papel** (no está en Notasnet);
   - si hay preferencias que debas respetar (por ejemplo, "no enviar correos sin mi ok", qué comentar al llegar notas nuevas).
5. Crea `colegio/` copiando las plantillas de `plantillas/`: `familia.md`, `estado.md`, `pendientes.md`, `notas.md`, `referencia.md`, y las carpetas `semanas/` y `archivo/`. Rellena `familia.md` con lo confirmado.
6. Rellena `referencia.md` con lo que Notasnet entregue sin esfuerzo (colegio, cursos, profesores jefe). El resto se va agregando con el uso. No inventes contactos ni horarios.
7. Primera sincronización: pregunta cuánto hacia atrás quiere revisar (por defecto, los últimos 30 días de comunicados y la agenda de las próximas 5 semanas) y ejecuta `colegio-actualizar` con ese límite, ya que aún no hay IDs registrados por canal.
8. Termina con un resumen corto: qué quedó configurado, lo urgente de los próximos 7 días y qué skills puede usar ahora.

## Notas
- No subas nada de `colegio/` a un repositorio público. Está en `.gitignore`; si el usuario quiere respaldarlo, que use un repositorio privado o un respaldo local.
