# Recursos de Claude en espanol para negocios mexicanos

Coleccion pequena y practica de prompts y "skills" de Claude (Anthropic),
en espanol, pensados para tareas administrativas comunes de una empresa
en Mexico: facturacion electronica (CFDI), avisos de privacidad (LFPDPPP)
y un par de tareas cotidianas mas.

No es un producto ni trabajo de cliente. Es un recurso abierto que
cualquiera puede copiar, adaptar y usar con Claude (via claude.ai,
la API de Anthropic o Claude Code).

## Aviso importante

- Todos los datos que aparecen en los ejemplos (RFC, montos, nombres,
  domicilios, correos) son **sinteticos / inventados**. No corresponden
  a ninguna persona, empresa o transaccion real.
- Estos prompts y skills son punto de partida educativo, no asesoria
  fiscal ni legal. Para CFDI, revisa siempre el Anexo 20 vigente del
  SAT. Para LFPDPPP, revisa con tu area legal antes de publicar un
  aviso de privacidad real.
- No subas aqui facturas, datos personales o informacion de clientes
  reales. Este repositorio se mantiene limpio de datos reales a
  proposito.

## Contenido

### `prompts/`

Prompts listos para copiar y pegar en claude.ai, la API, o cualquier
cliente de Claude. Cada archivo incluye: para que sirve, el prompt en
si, y un ejemplo de entrada/salida con datos sinteticos.

- `cfdi_validacion_basica.md` - revisar que un CFDI (factura
  electronica) tenga los campos minimos esperados y detectar errores
  comunes antes de timbrar o enviar.
- `lfpdppp_aviso_privacidad.md` - redactar o revisar un aviso de
  privacidad simplificado conforme a la LFPDPPP para una PyME.
- `recordatorio_cobranza.md` - generar recordatorios de pago
  (cobranza) con tono profesional y escalado segun dias de atraso.
- `resumen_minuta_reunion.md` - convertir notas sueltas de una
  reunion de trabajo en una minuta clara con acuerdos y responsables.

### `skills/`

Dos ejemplos de "Claude Skills" (carpeta con `SKILL.md` en formato
Agent Skills) que empaquetan el conocimiento de los dos prompts mas
especializados, para usarse con Claude Code o cualquier runtime que
soporte skills.

- `skills/cfdi-validador/` - skill para validar la estructura basica
  de un CFDI.
- `skills/lfpdppp-aviso-privacidad/` - skill para generar avisos de
  privacidad simplificados.

### `ejemplos/`

Datos de entrada sinteticos usados por los prompts/skills de arriba,
para que puedas probarlos sin exponer nada real:

- `cfdi_ejemplo_sintetico.xml`
- `aviso_privacidad_ejemplo_sintetico.txt`

## Como usarlos

1. Abre el prompt o el `SKILL.md` que te interese.
2. Copia el texto a claude.ai, a tu llamada a la API, o coloca la
   carpeta del skill donde tu cliente de Claude busque skills.
3. Sustituye los datos de ejemplo por los tuyos (reales, pero nunca
   los subas de vuelta a este repo).

## Licencia

MIT. Usa, copia y adapta libremente; ver `LICENSE`.

## Quienes somos

Mantenido por el equipo de AI Ethical Software / Expertos en Sistemas
(Mexico). Este repositorio es un recurso de la comunidad, no describe
nuestros productos ni resultados con clientes.
