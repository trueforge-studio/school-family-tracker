# Estado de sincronización

**Última sincronización con Notasnet:** (nunca). Comunicados revisados hasta: (ninguno). Agenda revisada hasta: (ninguna).

## Último comunicado procesado por canal
Al actualizar, en cada canal solo se procesan los ID mayores que estos (en `notasnet_list_communications`, el campo idEventData).

| Canal | Tipo | channelId | Último ID |
|---|---|---|---|

## Papel (agenda y panel)
(Qué se ingresó y cuándo.)

## Notas técnicas del MCP
- Los adjuntos no se pueden bajar con curl (403 sin la cookie). Si `get_attachment_content` devuelve un PDF vacío (por ejemplo, una imagen) o una tabla desordenada, revisarlo en Notasnet.
- `notasnet_get_agenda_events` falla con rangos largos cuando algún evento tiene `title: null`. Hay que pedir rangos de 1 semana o menos y, si falla, partir el rango en dos. En la agenda, los eventos `COM:` son comunicados (ya se cubren por canal); los que importan son los `EVE` (eventos) y los `PRU` (pruebas).
- Canales tipo `Acle` (academias) no se pueden listar con `list_communications` (solo acepta Colegio/Curso/Subsector): sus comunicados aparecen como `COM:` en la agenda; leerlos con `get_communication`.
- `notasnet_get_observations` puede fallar con zod cuando hay observaciones generales sin `Asig`, pero el cuerpo crudo viene en el mensaje de error y se puede leer igual.
- Comunicados con contenido en un PDF adjunto: leerlo con `notasnet_get_attachment_content`.
- Leer un comunicado no lo marca como leído: usar `notasnet_mark_notification_seen` con el `Sujeto` de la notificación.
