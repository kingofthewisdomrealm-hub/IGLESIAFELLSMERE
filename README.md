# Iglesia Nueva Vida Fellsmere — sitio web

Sitio estático de la iglesia. Producción: https://www.iglesianuevavidafellsmere.com

## Estructura

- `index.html` — el sitio completo: HTML, CSS y JS en un solo archivo
- `404.html` — página de error
- `vercel.json` — redirecciones (/contacto, /eventos, …) y cabeceras de caché
- `robots.txt`, `sitemap.xml` — SEO
- `media/` — fotos, video del hero, logos y fuentes

## Cómo está hecho

Sin framework, sin proceso de build. Se edita `index.html` y se despliega.
Tipografía: Montserrat (variable, servida localmente desde `media/fonts/`).

Paleta (definida en `:root`, derivada del logo de la iglesia):

| Token | Valor | Uso |
|---|---|---|
| `--navy` | `#00456B` | bandas de sección, pie, títulos |
| `--blue` | `#0089C4` | botones, íconos, acentos |
| `--blue-d` | `#006A94` | enlaces en texto (contraste AA) |
| `--orange` | `#F58220` | una sola acción por pantalla ("Dar") |
| `--ink` / `--muted` | `#1D2A32` / `#5B6B76` | texto |

El calendario se genera solo con la fecha actual (servicios de domingo, oración
de jueves, Santa Cena el 1er domingo, jóvenes el 3er jueves). Los eventos
especiales se agregan a mano en el objeto `SPECIAL` del primer `<script>`,
con clave `'AAAA-MM-DD'`.

El video del hero se aclara con un filtro CSS
(`brightness(1.42) contrast(.86) saturate(1.14)`), no con un velo blanco.

## Despliegue

Alojado en Vercel (proyecto `iglesia-nueva-vida`). El dominio sin www
redirige 308 al www. El correo de la iglesia está en Microsoft 365 — no tocar
los registros MX en GoDaddy.
