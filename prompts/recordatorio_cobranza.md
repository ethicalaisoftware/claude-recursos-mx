# Prompt: Recordatorio de cobranza (pago vencido)

## Para que sirve

Genera recordatorios de pago para clientes con facturas vencidas,
con tono profesional que escala segun los dias de atraso (cordial al
principio, mas firme si el atraso es mayor), comun en PyMEs
mexicanas que cobran por transferencia o deposito.

## Prompt

```
Eres un asistente que redacta recordatorios de cobranza en espanol,
tono mexicano de negocios (formal pero cercano, nunca agresivo).

Te dare: nombre del cliente, numero de factura, monto, fecha de
vencimiento, dias de atraso, y datos de pago.

Genera un correo corto (menos de 120 palabras) que:

1. Si el atraso es de 1 a 7 dias: tono de recordatorio amable,
   asumiendo que puede ser un olvido.
2. Si el atraso es de 8 a 30 dias: tono mas directo, pide fecha de
   pago y ofrece ayuda si hay algun problema.
3. Si el atraso es mayor a 30 dias: tono firme pero profesional,
   menciona que de no recibir respuesta se escalara el caso
   internamente, sin amenazar legalmente (eso lo decide la empresa,
   no el correo automatico).

No inventes montos, fechas ni datos de pago: usa exactamente los que
te proporcione. Si falta un dato, pide que se complete en vez de
inventarlo.

Datos:
Cliente: <<NOMBRE>>
Factura: <<FOLIO>>
Monto: <<MONTO>>
Vencimiento: <<FECHA>>
Dias de atraso: <<DIAS>>
Datos de pago: <<DATOS DE PAGO>>
```

## Ejemplo con datos sinteticos

Entrada:

```
Cliente: Comercializadora Rio Verde SA de CV (ficticia)
Factura: F-000123
Monto: $4,350.00 MXN
Vencimiento: 2026-09-15
Dias de atraso: 18
Datos de pago: transferencia a cuenta CLABE 000000000000000000 (ficticia)
```

Salida esperada (ejemplo, tono "8 a 30 dias"):

```
Asunto: Factura F-000123 pendiente de pago (18 dias de atraso)

Estimado equipo de Comercializadora Rio Verde,

Les escribimos para darle seguimiento a la factura F-000123 por
$4,350.00 MXN, con vencimiento el 15 de septiembre, que a la fecha
registra 18 dias de atraso.

Les pedimos nos confirmen una fecha de pago esta semana. Si hay algun
inconveniente con la factura o el servicio, con gusto lo revisamos.

Datos para el pago: transferencia a la cuenta CLABE indicada en la
factura original.

Quedamos atentos,
[Nombre / Area de cobranza]
```

(Nombre de cliente, folio, montos y CLABE son inventados solo para
este ejemplo.)
