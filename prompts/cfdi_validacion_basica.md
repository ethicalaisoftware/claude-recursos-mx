# Prompt: Validacion basica de un CFDI

## Para que sirve

Antes de timbrar o enviar un CFDI (Comprobante Fiscal Digital por
Internet), ayuda a revisar que los campos obligatorios esten
presentes, con formato razonable, y senala posibles errores comunes
(RFC mal formado, fechas inconsistentes, totales que no cuadran con
la suma de conceptos, etc.). No sustituye al validador oficial del
SAT ni a un contador; es una primera revision rapida.

## Prompt

```
Eres un asistente que revisa comprobantes fiscales (CFDI) mexicanos
ANTES de que se timbren o envien, buscando errores comunes. No tienes
que timbrar nada, solo revisar el texto/XML que te paso.

Revisa el siguiente CFDI (o sus datos clave) y responde con:

1. Campos obligatorios presentes / faltantes (RFC emisor, RFC
   receptor, fecha, folio, uso de CFDI, metodo de pago, forma de
   pago, moneda, subtotal, impuestos, total, conceptos).
2. Formato del RFC emisor y receptor (longitud y patron correctos
   para persona fisica o moral; no verifiques si existe en el SAT,
   solo el formato).
3. Consistencia aritmetica: subtotal + impuestos trasladados -
   impuestos retenidos = total (senala si no cuadra).
4. Consistencia de fechas (fecha de emision no futura, formato
   ISO 8601).
5. Cualquier otra inconsistencia obvia que seria motivo de rechazo
   por el receptor o por el PAC.

Da la respuesta como una lista corta de hallazgos, marcando cada uno
como [OK], [ADVERTENCIA] o [ERROR]. Al final, un veredicto de una
linea: "Listo para timbrar" o "Corregir antes de timbrar".

Importante: nunca asumas datos que no te di. Si falta informacion
para evaluar un punto, dilo explicitamente en vez de inventarla.

Aqui esta el CFDI:

<<PEGAR AQUI EL XML O LOS DATOS DEL CFDI>>
```

## Ejemplo con datos sinteticos

Entrada (ver `ejemplos/cfdi_ejemplo_sintetico.xml` para el XML
completo, con RFC y montos inventados):

```
Emisor RFC: AAA010101AAA, Receptor RFC: XYZ999999ZZ9
Fecha: 2026-13-45
Subtotal: 1000.00, IVA trasladado: 160.00, Total: 1150.00
Conceptos: 1 x "Servicio de consultoria" por 1000.00
```

Salida esperada (ejemplo):

```
- [ERROR] RFC receptor "XYZ999999ZZ9" no tiene un formato valido de
  RFC persona fisica (13 caracteres) ni persona moral (12
  caracteres) reconocible.
- [ERROR] Fecha "2026-13-45" no es una fecha calendario valida (mes
  13, dia 45 no existen).
- [ERROR] Total no cuadra: 1000.00 + 160.00 = 1160.00, pero el
  documento indica 1150.00.
- [OK] RFC emisor "AAA010101AAA" tiene formato de persona moral
  valido (12 caracteres).
- [OK] Subtotal coincide con la suma de conceptos (1000.00).

Veredicto: Corregir antes de timbrar.
```

(Los valores de este ejemplo son inventados unicamente para mostrar
el formato de salida.)
