---
name: lfpdppp-aviso-privacidad
description: Genera o revisa un borrador de aviso de privacidad simplificado conforme a la LFPDPPP mexicana (identidad del responsable, finalidades, derechos ARCO, transferencias, cambios al aviso) a partir de datos que da el usuario. Usar cuando el usuario pida redactar, generar o revisar un aviso de privacidad para una empresa en Mexico.
---

# Generador de aviso de privacidad simplificado (LFPDPPP)

Esta skill ayuda a producir un primer borrador de aviso de
privacidad simplificado, conforme a la Ley Federal de Proteccion de
Datos Personales en Posesion de los Particulares (LFPDPPP) de
Mexico. El resultado es siempre un borrador: debe revisarlo un
abogado especializado antes de publicarse.

## Cuando usar esta skill

Usa esta skill cuando el usuario pida redactar, generar o revisar un
aviso de privacidad para una empresa mexicana (tipicamente una
PyME).

## Datos que necesitas del usuario

Antes de generar el aviso, confirma que tienes (o pide lo que
falte):

1. Identidad y domicilio del responsable (nombre de la empresa y
   direccion).
2. Que datos personales recaba (ej. nombre, telefono, correo,
   direccion, datos de pago).
3. Para que los usa: separa finalidades primarias (indispensables
   para el servicio) de secundarias (ej. marketing).
4. Si comparte los datos con terceros, con quien y para que
   (ej. paqueteria, procesador de pagos).
5. Medio de contacto para ejercer derechos ARCO (correo, telefono,
   responsable de datos personales).

Si el usuario no da alguno de estos datos, NO lo inventes: usa un
marcador `[FALTA: dato especifico]` en el lugar correspondiente del
aviso.

## Estructura del aviso que debes generar

1. Identidad y domicilio del responsable.
2. Finalidades del tratamiento (primarias y secundarias, separadas).
3. Mecanismo para negar o revocar el consentimiento a finalidades
   secundarias.
4. Medios para ejercer derechos ARCO (Acceso, Rectificacion,
   Cancelacion, Oposicion) y, si aplica, revocar consentimiento o
   limitar uso/divulgacion.
5. Transferencias de datos a terceros, si existen, y su finalidad.
6. Como se notificaran cambios futuros al aviso de privacidad.

## Nota de cierre obligatoria

Siempre termina el aviso generado con esta nota, sin modificarla:

> Este documento es un borrador generado con ayuda de IA. Debe ser
> revisado y validado por un abogado especializado en proteccion de
> datos antes de publicarse o usarse.

## Reglas importantes

- No eres abogado; no afirmes que el aviso cumple la ley, solo que
  sigue la estructura minima esperada.
- Nunca uses datos reales de clientes o empleados para probar esta
  skill: usa datos sinteticos (ver
  `ejemplos/aviso_privacidad_ejemplo_sintetico.txt` en la raiz del
  repositorio).
- Si el usuario pide un aviso "integral" (no simplificado, con mas
  requisitos formales), acláralo: esta skill produce la version
  simplificada; sugiere asesoria legal para la version integral.
