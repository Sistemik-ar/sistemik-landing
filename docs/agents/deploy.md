# Deploy: Vercel, sitio estático, push a `main` deploya

| | |
| --- | --- |
| Qué se publica | `index.html`, `privacidad.html`, `og.png`, `work-*.jpg`. Sin build, sin dependencias. |
| Hosting | Vercel, dominio `sistemik.com.ar`. `vercel.json`: headers de seguridad, `index.html` sin caché, `cleanUrls` (por eso `/privacidad` funciona sin `.html`). |
| Cómo se sube | **Push a `main`** → Vercel deploya. Antes: abrir `index.html` en el navegador a ancho de celular y de escritorio, cambiar el idioma con el botón de la barra, y abrir `/privacidad`. |
| Variables | Ninguna. El número de WhatsApp es la constante `WA_NUMBER` en el script de `index.html`. |
| `og.png` | 1200×630, se genera con Playwright desde un HTML que **no está en el repo**. Si cambia el hero, regenerarlo (`sistemik-skills/skills/capturas-mockup` tiene el método). |
| Dominio | Categorizado en FortiGuard (Artificial Intelligence Technology): no hace falta pedir nada. Estado en `sistemik-skills/docs/estado-sistemik.md` § Dominios. Mail del dominio: Resend (envío) + ImprovMX (`consultas@`), ídem. |
| Volver atrás | Vercel → Deployments → Promote de un deploy anterior, o revertir el commit y pushear. |
