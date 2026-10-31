# Prompt: Minuta de reunion a partir de notas sueltas

## Para que sirve

Convierte notas desordenadas tomadas durante una reunion de trabajo
(texto libre, puntos sueltos, a veces en espanol mezclado con
ingles) en una minuta clara: temas tratados, acuerdos, responsables y
fechas compromiso. Util para equipos pequenos que no usan un sistema
formal de actas.

## Prompt

```
Eres un asistente que convierte notas de reunion, tomadas de forma
desordenada, en una minuta clara en espanol.

A partir de las notas que te paso, genera una minuta con esta
estructura:

1. Fecha y asistentes (si no estan en las notas, escribe
   "[FALTA: dato]" en vez de inventarlos).
2. Temas tratados (lista corta, en el orden en que se mencionaron).
3. Acuerdos y compromisos, cada uno con: que se acordo, quien es
   responsable, y fecha compromiso (si no hay responsable o fecha
   explicitos en las notas, escribe "[FALTA: responsable]" o
   "[FALTA: fecha]" en vez de adivinar).
4. Pendientes para la siguiente reunion.

No agregues acuerdos que no esten claramente respaldados por las
notas. Si una nota es ambigua, incluyela en "Pendientes" con una nota
de que necesita aclararse, en vez de interpretarla.

Notas de la reunion:

<<PEGAR AQUI LAS NOTAS>>
```

## Ejemplo con datos sinteticos

Entrada:

```
junta lunes equipo ventas, estuvieron Luis y Marcela (ficticios)
hablamos de bajar precio paquete basico? marcela dice revisar con
finanzas. luis se compromete a mandar propuesta nueva lista precios
antes del viernes. pendiente ver tema de descuentos por volumen, no
se decidio nada
```

Salida esperada (ejemplo):

```
Minuta de reunion

Fecha: [FALTA: fecha exacta, solo se menciona "lunes"]
Asistentes: Luis, Marcela (ficticios)

Temas tratados:
- Posible reduccion de precio del paquete basico
- Propuesta de nueva lista de precios
- Descuentos por volumen

Acuerdos y compromisos:
- Revisar con finanzas la posible baja de precio del paquete basico.
  Responsable: Marcela. Fecha compromiso: [FALTA: fecha]
- Enviar propuesta de nueva lista de precios. Responsable: Luis.
  Fecha compromiso: antes del viernes.

Pendientes para la siguiente reunion:
- Descuentos por volumen: no se tomo ninguna decision, queda
  abierto para la siguiente junta.
```

(Nombres y contenido son inventados solo para este ejemplo.)
