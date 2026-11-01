# Prompt: Resumir y clasificar notificaciones del Buzon Tributario (SAT)

## Para que sirve

El Buzon Tributario del SAT envia notificaciones (requerimientos,
avisos, invitaciones, resoluciones, etc.) que a veces son dificiles
de leer rapido por su lenguaje formal. Este prompt ayuda a resumir en
lenguaje sencillo el contenido de una o varias notificaciones, y a
clasificarlas por urgencia, para decidir cuales necesitan atencion
inmediata (por ejemplo, las que tienen un plazo legal) y cuales son
solo informativas. No sustituye la lectura completa del documento
oficial ni la opinion de un contador o abogado fiscal; es una primera
lectura para priorizar.

## Prompt

```
Eres un asistente que ayuda a resumir y clasificar notificaciones del
Buzon Tributario del SAT (Mexico) en lenguaje sencillo. No eres
contador ni abogado fiscal: tu resumen es solo para priorizar, nunca
para decidir una respuesta legal o fiscal sin validarla con un
profesional.

Te voy a dar el texto de una o varias notificaciones del Buzon
Tributario (copiado y pegado, sin adjuntos). Para cada notificacion,
responde con:

1. Tipo de notificacion (por ejemplo: requerimiento, invitacion,
   resolucion, aviso informativo, carta invitacion, multa).
2. Resumen en 2-3 lineas, en espanol sencillo, de que pide o informa
   el SAT.
3. Si existe un plazo o fecha limite mencionada en el texto, indicala
   textualmente; si no se menciona ningun plazo, dilo explicitamente
   (no inventes una fecha).
4. Clasificacion de urgencia: [URGENTE] si hay un plazo legal
   proximo o riesgo de multa/embargo mencionado en el texto,
   [REVISAR] si pide una accion pero sin plazo inmediato claro, o
   [INFORMATIVA] si es solo un aviso sin accion requerida.
5. Una linea de "siguiente paso sugerido" en terminos generales (por
   ejemplo: "revisar con el contador antes de la fecha limite"), sin
   dar asesoria fiscal especifica.

Al final de todo el reporte agrega esta nota fija:
"Este resumen es solo para priorizar la lectura de tus notificaciones
del SAT. No es asesoria fiscal ni legal. Consulta siempre el
documento original en el Buzon Tributario y a tu contador o abogado
fiscal antes de responder o dejar pasar un plazo."

Importante: no inventes plazos, montos ni articulos legales que no
esten explicitos en el texto que te doy. Si el texto esta incompleto
o es ambiguo, dilo en vez de adivinar.

Aqui estan las notificaciones:

<<PEGAR AQUI EL TEXTO DE LAS NOTIFICACIONES DEL BUZON TRIBUTARIO>>
```

## Ejemplo con datos sinteticos

Entrada (ver tambien `ejemplos/buzon_tributario_ejemplo_sintetico.txt`),
dos notificaciones ficticias para una empresa inventada:

```
Notificacion 1:
Contribuyente: Ferreteria El Tornillo Feliz SA de CV, RFC AAA010101AAA
Asunto: Requerimiento de informacion y/o documentacion
Texto: Se requiere al contribuyente exhibir la documentacion
comprobatoria de las operaciones declaradas en el periodo enero-marzo
2026, en un plazo de 15 dias habiles contados a partir de la fecha de
notificacion. El incumplimiento podra dar lugar a la imposicion de
las multas previstas en el Codigo Fiscal de la Federacion.

Notificacion 2:
Contribuyente: Ferreteria El Tornillo Feliz SA de CV, RFC AAA010101AAA
Asunto: Aviso informativo sobre actualizacion del aplicativo de
Buzon Tributario
Texto: Se informa que el aplicativo del Buzon Tributario tendra
mantenimiento el fin de semana proximo. No se requiere ninguna accion
por parte del contribuyente.
```

Salida esperada (ejemplo):

```
Notificacion 1
- Tipo: Requerimiento de informacion y/o documentacion.
- Resumen: El SAT pide que la empresa muestre la documentacion que
  respalda las operaciones declaradas de enero a marzo de 2026.
- Plazo: 15 dias habiles desde la fecha de notificacion (el texto no
  da una fecha calendario exacta).
- Urgencia: [URGENTE] - hay un plazo legal y riesgo de multa
  mencionado explicitamente.
- Siguiente paso sugerido: reunir la documentacion del periodo y
  revisarla con el contador antes de que venza el plazo.

Notificacion 2
- Tipo: Aviso informativo.
- Resumen: El Buzon Tributario tendra mantenimiento el proximo fin de
  semana; no hay ninguna accion pendiente para la empresa.
- Plazo: no se menciona ningun plazo ni accion requerida.
- Urgencia: [INFORMATIVA] - no pide ninguna accion.
- Siguiente paso sugerido: ninguno, solo tomar nota.

Este resumen es solo para priorizar la lectura de tus notificaciones
del SAT. No es asesoria fiscal ni legal. Consulta siempre el
documento original en el Buzon Tributario y a tu contador o abogado
fiscal antes de responder o dejar pasar un plazo.
```

(Los datos de este ejemplo - empresa, RFC y notificaciones - son
inventados unicamente para mostrar el formato de salida.)
