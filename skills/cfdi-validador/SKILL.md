---
name: cfdi-validador
description: Revisa un CFDI (factura electronica mexicana) buscando campos faltantes, RFC mal formados, fechas invalidas e inconsistencias aritmeticas entre subtotal, impuestos y total, antes de timbrar o enviar. Usar cuando el usuario pida validar, revisar o detectar errores en un CFDI/factura/XML fiscal mexicano.
---

# Validador basico de CFDI

Esta skill ayuda a revisar, antes de timbrar o enviar, que un CFDI
(Comprobante Fiscal Digital por Internet) mexicano tenga los campos
minimos y no tenga errores obvios. No sustituye al validador oficial
del SAT ni a un contador: es una primera revision automatica.

## Cuando usar esta skill

Usa esta skill cuando el usuario comparta el XML o los datos de un
CFDI y pida revisarlo, validarlo, o detectar por que podria ser
rechazado.

## Como revisar

Al recibir el CFDI (XML completo o los campos clave en texto),
revisa en este orden:

1. **Campos obligatorios presentes**: RFC emisor, RFC receptor,
   fecha de emision, folio, uso de CFDI, metodo de pago, forma de
   pago, moneda, subtotal, impuestos, total, y al menos un
   concepto. Marca cualquier campo ausente.

2. **Formato de RFC**: persona fisica = 13 caracteres
   (4 letras + 6 digitos de fecha + 3 caracteres homoclave);
   persona moral = 12 caracteres (3 letras + 6 digitos de fecha +
   3 caracteres homoclave). Solo valida el formato/longitud, no
   verifiques existencia real ante el SAT (no tienes esa
   informacion).

3. **Fechas**: la fecha de emision debe ser una fecha calendario
   valida (sin meses >12 ni dias que no existan) y no debe ser
   futura respecto a cuando se esta revisando.

4. **Consistencia aritmetica**: subtotal + impuestos trasladados -
   impuestos retenidos debe ser igual al total (tolerancia de
   redondeo de un centavo). Tambien verifica que el subtotal
   corresponda a la suma de los conceptos si estan desglosados.

5. **Otras inconsistencias obvias**: moneda sin tipo de cambio
   cuando no es MXN, uso de CFDI que no aplica al tipo de receptor,
   etc. Senala solo lo que puedas verificar con los datos dados.

## Formato de respuesta

Lista de hallazgos, cada uno marcado `[OK]`, `[ADVERTENCIA]` o
`[ERROR]`, seguido de un veredicto de una linea: "Listo para
timbrar" o "Corregir antes de timbrar".

## Reglas importantes

- Nunca inventes o asumas un dato que no este en el CFDI dado. Si
  falta informacion para evaluar un punto, dilo explicitamente
  ("no se puede verificar X por falta de Y") en vez de asumir que
  esta bien.
- Nunca uses ni pidas datos reales de clientes para probar esta
  skill: usa siempre datos sinteticos (ver
  `ejemplos/cfdi_ejemplo_sintetico.xml` en la raiz del repositorio).
- Esto es una revision de forma, no asesoria fiscal. Si el usuario
  tiene duda sobre si un CFDI es fiscalmente correcto (no solo bien
  formado), sugiere consultar a su contador.
