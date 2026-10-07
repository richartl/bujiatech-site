# CLAUDE.md: sitio de Bujia Tech

Contexto para trabajar en este repositorio. Léelo completo antes de tocar algo.

## Qué es Bujia Tech
La empresa de software de Ricardo Pérez, ingeniero en sistemas: desarrollo de software a la medida, nube, soluciones híbridas (nube + equipo local) y consultoría. Su producto principal es **BujiOps** (https://bujiops.app/), un CRM para talleres de reparación que nació para administrar Bujia Project Music, el taller de guitarras y bajos de Ricardo en Texcoco, Estado de México. BujiOps es la prueba de lo que Bujia Tech sabe construir: está en producción, corre en la nube (Docker en DigitalOcean con Caddy, CI/CD con GitHub Actions, GCS) e imprime con hardware real (agente en Rust con una Brother QL-800).

## Para qué es este sitio
Una landing de una sola página más el aviso de privacidad. Su único objetivo es que un prospecto entienda qué hace Bujia Tech, le crea (gracias a BujiOps) y escriba. **CTA principal:** «Cuéntanos tu proyecto» → WhatsApp propio de Bujia Tech. **Secundario:** «Ver BujiOps» → https://bujiops.app/.

**Audiencia:** dueños y encargados de talleres, comercios y pymes en México que necesitan un sistema, publicarlo en la nube o conectarlo con equipo en su local, y que en general llegan desde el celular.

## Idioma y tono
- Español de México (`lang="es-MX"`). Se le habla de **tú** al lector, sin excepción y en todo el sitio. El aviso de privacidad también va de tú.
- Técnico pero cercano, directo, frases cortas. Sin buzzwords («transformación digital», «disruptivo», «sinergia», «de clase mundial»).
- Cada afirmación tiene que ser verdad **hoy** y poder demostrarse. Si no, no se dice.

## Fuente de verdad del contenido
`docs/contenido-landing.md`. El HTML copia ese texto **literalmente**. Si un texto hace falta o se ve mal, no lo reescribas en el HTML: proponlo en el PR como cambio al documento. Las líneas `[PENDIENTE: ...]` no se muestran en la página (cuando aplica se dejan como comentario HTML).

## Restricciones técnicas
- **Solo sitio estático**: HTML + CSS + imágenes. Sin build, sin `package.json`, sin frameworks, sin JavaScript y sin tipografía web. Un paso de build solo se agrega con una justificación escrita en el issue y aprobada por Ricardo.
- Se publica en **GitHub Pages** con `.github/workflows/publicar.yml` (mismo patrón que `richartl/bujiops.app`). El job `revisar` corre en PR; `publicar` solo en `main`. Se publica una lista explícita de archivos: `CLAUDE.md`, `README.md`, `docs/` y `.github/` no se publican.
- Las rutas internas son **relativas** (sin `/` inicial), para que el sitio funcione en `richartl.github.io/bujiatech-site/` y en el dominio propio.
- **Dominio:** todavía no existe. Usa el marcador literal `{{DOMINIO}}` (sin `https://` ni `/` final) en `CNAME`, canonical, `og:url`, `og:image`, `twitter:image`, `sitemap.xml` y `robots.txt`. Esas URL son absolutas: `https://{{DOMINIO}}/...`. No inventes un dominio ni uses el de github.io en los metadatos. Con despliegue por Actions, el dominio real se configura en *Settings → Pages*; `CNAME` queda como registro.
- **Otros marcadores** (se dejan tal cual hasta que Ricardo dé el dato): `{{WHATSAPP}}` (52 + 10 dígitos, para `wa.me`), `{{TELEFONO_VISIBLE}}`, `{{CORREO}}`, `{{CORREO_PRIVACIDAD}}`, `{{RESPONSABLE}}`, `{{DOMICILIO}}`, `{{FECHA_AVISO}}`. El workflow avisa (no bloquea) mientras sigan ahí.
- Imágenes en WebP con `width`/`height` y `loading="lazy"` debajo del pliegue. La tarjeta OG va en **JPEG** 1200×630 (WhatsApp no lee WebP de forma confiable).
- Paleta provisional en variables CSS en `:root` (la de BujiOps: slate + ámbar) hasta que exista la marca de Bujia Tech. Contraste AA medido, no a ojo.

## Estructura
```
.github/workflows/publicar.yml   CLAUDE.md   README.md   docs/contenido-landing.md
index.html   aviso-de-privacidad.html   base.css   CNAME   robots.txt   sitemap.xml
favicon.svg   favicon-32.png   apple-touch-icon.png   img/ (og.jpg + WebP)
```

## Convenciones
- **Ramas:** `issue-<número>-<descripcion-corta>` desde `main`, p. ej. `issue-1-landing-inicial`.
- **Commits:** en español, en imperativo, con prefijo: `feat:`, `fix:`, `docs:`, `ci:`, `chore:`. Ejemplo: `feat: agrega sección de servicios`. Commits pequeños y con sentido propio.
- Comentarios en HTML/CSS/YAML en español y explicando el *porqué*, no el qué (como en bujiops.app).
- **PR:** el título es el del issue; la descripción empieza con `Cierra #<número>` y tiene **una línea por cada casilla del issue**, con su número y su evidencia (comando + salida, captura, enlace al reporte de Lighthouse/axe). Si una casilla no se cumple, se dice y se explica por qué. Rony revisa contra esas casillas y Ricardo hace el merge. No hagas merge tú.

## Definición de terminado
1. Se cumplen todas las casillas de criterios de aceptación del issue, con evidencia en el PR.
2. El check `revisar` está en verde (los warnings de marcadores son esperados).
3. En local (`python3 -m http.server 4500`): sin scroll horizontal a 360, 768 y 1280 px; axe sin violaciones; Lighthouse móvil ≥ 90 en las cuatro categorías.
4. El texto coincide con `docs/contenido-landing.md`.

## No hagas esto
- **No uses el WhatsApp del taller (5618622447), ni el correo del taller, ni `bujiopsapp@gmail.com`.** El contacto es de Bujia Tech; mientras no exista se usan los marcadores.
- No inventes clientes, testimonios, logos de clientes, cifras, años de experiencia, certificaciones ni tamaño del equipo. Tampoco funciones de BujiOps que no estén en el documento.
- No agregues analítica, píxeles, rastreadores, cookies, fuentes externas, CDN ni ningún recurso de terceros.
- No hagas commit de secretos, `.env`, tokens ni llaves. Este sitio no necesita ninguno.
- No agregues formularios con backend ni Formspree (fuera de alcance en la v1).
- No toques `richartl/bujiops.app` ni el producto BujiOps desde este repo.
- No reemplaces los marcadores con datos supuestos.
