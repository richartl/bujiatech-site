# bujiatech-site

Landing de una página de **Bujia Tech** (software a la medida, nube, soluciones híbridas y consultoría) más su aviso de privacidad. HTML y CSS a mano: sin build, sin dependencias y sin JavaScript. Se publica en GitHub Pages.

El texto del sitio sale de [`docs/contenido-landing.md`](docs/contenido-landing.md): si hay que cambiar un texto, se cambia primero ahí. Las reglas de trabajo están en [`CLAUDE.md`](CLAUDE.md).

## Verlo en local

```sh
python3 -m http.server 4500
```

y abre <http://localhost:4500/>. Abrir el archivo directo (`file://`) no sirve: las rutas relativas como `./` no resuelven a `index.html`.

## Qué se publica

Solo lo que está en la variable `PUBLICAR` de [`.github/workflows/publicar.yml`](.github/workflows/publicar.yml):

```
index.html  aviso-de-privacidad.html  base.css  CNAME  robots.txt  sitemap.xml
favicon.svg  favicon-32.png  apple-touch-icon.png  img/
```

`CLAUDE.md`, `README.md`, `docs/` y `.github/` se quedan en el repo y **no** llegan a Pages. Si agregas un archivo al sitio, agrégalo también a esa lista o no saldrá (el job `revisar` falla si una página lo enlaza y no está).

## Cómo se publica

Cada push a `main` corre el workflow **Revisar y publicar**:

1. **`revisar`** (también corre en cada PR): falla si falta un archivo del sitio, si una página enlaza un archivo local que no se publica, si hay `<script>`, si `sitemap.xml` no es XML válido o si aparece el WhatsApp o el correo del taller. Por cada marcador `{{...}}` o `[PENDIENTE` que siga en lo publicado deja un *warning*, sin bloquear.
2. **`publicar`**: solo en `main` (push o a mano desde *Actions → Run workflow*) y solo si `revisar` pasó. Arma `_site/` y lo despliega.

### La primera vez

- **Prende Pages a mano:** *Settings → Pages → Source: GitHub Actions*. El workflow no lo puede prender solo; si falla con "Get Pages site failed", es que sigue apagado.
- **Dominio propio:** con despliegue por Actions, GitHub **no lee** el archivo `CNAME`. El dominio se configura en *Settings → Pages → Custom domain* y, cuando el DNS ya apunte, se activa *Enforce HTTPS*. El archivo `CNAME` se queda en el repo como registro del dominio que se usa, pero no lo configura.

Mientras no haya dominio, el sitio funciona en `https://richartl.github.io/bujiatech-site/` porque todas las rutas internas son relativas.

## Reemplazar los marcadores

El dominio y los datos de contacto y legales todavía no existen; el sitio usa marcadores literales (tabla completa en la sección 13 de `docs/contenido-landing.md`). Cuando Ricardo dé un dato, se reemplaza en **todos** los archivos con un solo comando desde la raíz del repo (los ejemplos usan datos de muestra):

```sh
git grep -l '{{DOMINIO}}'            | xargs sed -i 's/{{DOMINIO}}/ejemplo.mx/g'
git grep -l '{{WHATSAPP}}'           | xargs sed -i 's/{{WHATSAPP}}/525512345678/g'
git grep -l '{{TELEFONO_VISIBLE}}'   | xargs sed -i 's/{{TELEFONO_VISIBLE}}/55 1234 5678/g'
git grep -l '{{CORREO_PRIVACIDAD}}'  | xargs sed -i 's/{{CORREO_PRIVACIDAD}}/privacidad@ejemplo.mx/g'
git grep -l '{{CORREO}}'             | xargs sed -i 's/{{CORREO}}/contacto@ejemplo.mx/g'
git grep -l '{{RESPONSABLE}}'        | xargs sed -i 's/{{RESPONSABLE}}/Nombre o razón social/g'
git grep -l '{{DOMICILIO}}'          | xargs sed -i 's/{{DOMICILIO}}/Calle, número, colonia, municipio, estado, CP/g'
git grep -l '{{FECHA_AVISO}}'        | xargs sed -i 's/{{FECHA_AVISO}}/7 de octubre de 2026/g'
```

Notas:

- `{{DOMINIO}}` va **sin** `https://` ni `/` final (`ejemplo.mx`, no `https://ejemplo.mx/`).
- `{{WHATSAPP}}` es `52` + 10 dígitos, sin espacios ni `+`, porque va dentro de `https://wa.me/...`. Es el número **de Bujia Tech**, nunca el del taller.
- Si un valor lleva `/` o `&`, escápalo en `sed` (`\/`, `\&`) o usa otro separador: `sed -i 's|{{DOMICILIO}}|Av. 5 de Mayo 1/2|g'`.
- `git grep` también encuentra los marcadores en `CLAUDE.md`, `README.md` y `docs/`, que documentan cómo se usan. Si no quieres tocarlos, limita el comando a lo publicado: `git grep -l '{{DOMINIO}}' -- ':!CLAUDE.md' ':!README.md' ':!docs'`.

Después de reemplazar, corre `git grep -n '{{'` para ver qué falta; los *warnings* del job `revisar` desaparecen solos.

## Antes de aprobar una versión

- Sin scroll horizontal a 360, 768 y 1280 px (`document.documentElement.scrollWidth <= window.innerWidth` en la consola).
- axe (WCAG 2.2 AA) sin violaciones a 360 y 1280 px, en las dos páginas.
- Lighthouse móvil ≥ 90 en las cuatro categorías: `npx lighthouse http://localhost:4500/ --form-factor=mobile`.
- El texto coincide con `docs/contenido-landing.md`.
- Ni el WhatsApp ni el correo del taller aparecen en lo publicado (el job `revisar` lo comprueba).
