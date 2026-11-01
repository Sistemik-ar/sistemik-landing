# CLAUDE.md — cómo se trabaja en este proyecto

**sistemik.com.ar**, la landing de Sistemik. Vende el modelo actual: software y bots de
WhatsApp para pymes de Bariloche, con **Estudio** (producto para estudios contables) como
caso principal, servicios, trabajos (Bandurrias, Paola, Poli, Repuestos), proceso en 4
pasos con las condiciones comerciales, y contacto que arma un mensaje de WhatsApp. ES/EN.
`/privacidad` es la política que exige la app de Meta: **no romper esa URL**.

Quien la lee es un dueño de pyme o un contador de Bariloche, casi siempre desde el
celular, que llegó por un mensaje de Felipe. Tiene que entender en 10 segundos qué
hacemos y cuánto sale.

## Fuentes de verdad, en orden

1. `/Users/feliarana/Projects/sistemik/sistemik-skills`: `docs/proyectos.md` (la entrada
   de esta landing, con qué secciones tiene y por qué), y
   `skills/propuesta-cliente/references/precios.md` (las condiciones comerciales que la
   landing muestra: sin costo inicial, sin permanencia, precio fijo 12 meses, por
   etapas). **Si cambian ahí, cambiar acá.**
2. `index.html`. Es un solo archivo con CSS y JS adentro, a propósito: sin build.

## Reglas duras

- **Todos los textos viven en el diccionario `T`** del script, con claves `data-i18n` en
  el HTML, en ES y EN. Un texto nuevo va a las dos lenguas o no va. No escribas texto
  suelto en el HTML.
- Los mockups del teléfono y del chat de WhatsApp son **HTML/CSS, no imágenes**; se
  editan como el resto de la página.
- El número de WhatsApp es la constante `WA_NUMBER`. Un solo lugar.
- Sin dependencias, sin framework, sin build. Si algo "necesita" npm, no va en esta landing.
- `privacidad.html` es un requisito de Meta: cambiarla sólo con Felipe, y la URL
  `https://sistemik.com.ar/privacidad` no se mueve.
- **Push a `main` es publicar** (Vercel). Antes, mirar la página a ancho de celular y de
  escritorio en los dos idiomas. Detalle: `docs/agents/deploy.md`.

## Idioma

Conversación, docs y commits en español rioplatense con acentos. Commits escritos desde
lo que ve quien entra a la página: `Rediseño de la landing: Estudio, bots de WhatsApp y
abono mensual, en desktop y mobile`.

## Método de trabajo

- Un cambio a la vez, commits chicos.
- Los textos de venta (precios, condiciones, qué incluye Estudio) los decide Felipe; si
  hay que inventar uno, proponé dos opciones en vez de escribirlo.
- Lo que aprendas que sirva a otro proyecto (Vercel, dominios, Meta) va a sistemik-skills
  con `/documentar`.

## Agent skills

### Issue tracker

GitHub Issues de `Sistemik-ar/sistemik-landing`, con `gh`. Ver `docs/agents/issue-tracker.md`.

### Triage labels

Las cinco etiquetas canónicas (`needs-triage`, `needs-info`, `ready-for-agent`,
`ready-for-human`, `wontfix`), creadas en el repo el 01/11/2026. Ver `docs/agents/triage-labels.md`.

### Domain docs

Single-context: `GLOSSARY.md` y `docs/adr/` en la raíz, se crean cuando haga falta. Ver
`docs/agents/domain.md`.

### Deploy

Vercel; push a `main` publica. Sin base de datos. Ver `docs/agents/deploy.md`.
