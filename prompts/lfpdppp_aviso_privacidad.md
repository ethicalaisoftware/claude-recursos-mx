# Prompt: Redactar o revisar un aviso de privacidad (LFPDPPP)

## Para que sirve

Ayuda a una PyME mexicana a redactar un primer borrador de aviso de
privacidad simplificado, o a revisar uno existente contra los
elementos minimos que marca la Ley Federal de Proteccion de Datos
Personales en Posesion de los Particulares (LFPDPPP) y sus
lineamientos. Es un punto de partida: el borrador debe revisarlo
siempre tu area legal antes de publicarlo.

## Prompt

```
Eres un asistente que ayuda a redactar/revisar avisos de privacidad
simplificados conforme a la LFPDPPP (Mexico). No eres abogado y tu
borrador siempre debe ser revisado por asesoria legal antes de
publicarse; dilo explicitamente al final de tu respuesta.

Te voy a dar datos de una empresa (nombre, a que se dedica, que
datos personales recaba y para que, si comparte datos con terceros y
con quien, y sus datos de contacto para ejercer derechos ARCO).

Con esos datos, genera un AVISO DE PRIVACIDAD SIMPLIFICADO que
incluya como minimo:

1. Identidad y domicilio del responsable.
2. Finalidades del tratamiento de datos personales (separa
   finalidades primarias de las secundarias/no indispensables).
3. Mecanismo para que el titular pueda negar o revocar su
   consentimiento a finalidades secundarias.
4. Medios para ejercer los derechos ARCO (Acceso, Rectificacion,
   Cancelacion, Oposicion) y, si aplica, revocar el consentimiento o
   limitar el uso/divulgacion de sus datos.
5. En su caso, las transferencias de datos que se realicen y su
   finalidad.
6. Como se comunicaran cambios al aviso de privacidad.

Si te falta algun dato para completar una seccion, NO lo inventes:
deja un marcador tipo [FALTA: dato especifico] para que lo complete
la empresa.

Al final agrega esta nota fija:
"Este documento es un borrador generado con ayuda de IA. Debe ser
revisado y validado por un abogado especializado en proteccion de
datos antes de publicarse o usarse."

Datos de la empresa:

<<PEGAR AQUI LOS DATOS DE LA EMPRESA>>
```

## Ejemplo con datos sinteticos

Entrada (ver tambien `ejemplos/aviso_privacidad_ejemplo_sintetico.txt`):

```
Empresa: "Ferreteria El Tornillo Feliz SA de CV" (ficticia)
Domicilio: Calle Falsa 123, Col. Centro, Guadalajara, Jalisco (ficticio)
Datos que recaba: nombre, telefono, correo, direccion de entrega
Finalidad primaria: procesar pedidos y entregas
Finalidad secundaria: enviar promociones por correo
Comparte datos con: paqueteria externa, solo para hacer la entrega
Contacto ARCO: privacidad@ejemplo-ficticio.mx (ficticio)
```

Salida esperada: un aviso de privacidad simplificado con las 6
secciones anteriores, usando esos datos ficticios, con marcadores
`[FALTA: ...]` donde algo no se haya proporcionado (por ejemplo, el
procedimiento exacto para revocar consentimiento si no se describio),
y terminando con la nota de revision legal obligatoria.
