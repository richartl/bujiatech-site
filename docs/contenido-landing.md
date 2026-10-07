# Contenido de la landing de Bujia Tech

> **Fuente de verdad del texto del sitio.** El HTML copia este documento literalmente: lo que no está aquí no va en la página.
> Versión 1 · 7 de octubre de 2026 · Idioma: español de México (es-MX).
>
> **Marcadores:**
> - `{{...}}`: dato que se reemplaza en bloque cuando exista (dominio, WhatsApp, correo, datos legales). La tabla completa está en la sección 13.
> - `[PENDIENTE: ...]`: decisión o contenido que Ricardo tiene que dar. **Nunca se inventa**: no se ponen clientes, testimonios, cifras, años de experiencia, certificaciones ni tamaño del equipo.

---

## 1. Tono

Técnico pero cercano, y directo. Le hablamos de **tú** al lector (como bujiops.app), en frases cortas y con verbos concretos: *construimos*, *publicamos*, *conectamos*. Nada de buzzwords («transformación digital», «soluciones disruptivas», «sinergia», «de clase mundial»). Cada afirmación se respalda con algo que ya existe y funciona, y la prueba principal es BujiOps: un sistema que hicimos, que publicamos en la nube y que opera en producción en un taller real, impresora de etiquetas incluida. Si algo no lo podemos demostrar, no lo decimos.

## 2. Llamados a la acción (CTA)

| | Texto del botón | Destino | Por qué |
|---|---|---|---|
| **Principal** | **Cuéntanos tu proyecto** | `https://wa.me/{{WHATSAPP}}?text=Hola%2C%20vengo%20del%20sitio%20de%20Bujia%20Tech%20y%20quiero%20platicar%20de%20un%20proyecto.` | En México los negocios que nos interesan (talleres, comercios, pymes) contestan por WhatsApp antes que por correo. El sitio es estático y sin backend, así que un enlace `wa.me` con el mensaje ya escrito es el camino más corto y no necesita servicios de terceros. Usamos un número **propio de Bujia Tech**, nunca el del taller. |
| **Secundario** | **Ver BujiOps** | `https://bujiops.app/` | Quien todavía no está listo para escribir necesita una prueba. BujiOps es un producto real y en línea: verlo funcionando convence más que cualquier párrafo. Abre en la misma pestaña (sin `target="_blank"`). |
| Alternativo (solo en Contacto y pie) | Escríbenos un correo | `mailto:{{CORREO}}?subject=Proyecto%20desde%20el%20sitio` | Para quien prefiere el correo o necesita mandar documentos. |

---

## 3. SEO y tarjeta para compartir

| Campo | Texto |
|---|---|
| `<title>` | Bujia Tech — Software a la medida, nube y consultoría |
| `meta description` (146 car.) | Desarrollamos software a la medida, soluciones en la nube e híbridas, y consultoría técnica. Somos los creadores de BujiOps, el CRM para talleres. |
| `og:title` / `twitter:title` | Software que aguanta el día a día de tu negocio |
| `og:description` / `twitter:description` | Software a la medida, en la nube y conectado a tu local. Lo probamos primero en casa: BujiOps opera en producción en un taller real. |
| `og:url` / canonical | `https://{{DOMINIO}}/` |
| `og:image` / `twitter:image` | `https://{{DOMINIO}}/img/og.jpg` (1200×630, JPEG) |
| `og:image:alt` | Bujia Tech: software a la medida, nube y consultoría |
| `og:site_name` | Bujia Tech |
| `og:locale` | es_MX |

**Imagen OG (texto de la tarjeta):** «Bujia Tech» en grande y debajo «Software a la medida · Nube · Consultoría». Mientras no haya logo [PENDIENTE: logo], se hace solo con tipografía y la paleta provisional.

---

## 4. Navegación (encabezado)

- Marca: **Bujia Tech** (texto; se cambia por el logo cuando exista)
- Enlaces: Servicios (`#servicios`) · BujiOps (`#bujiops`) · Cómo trabajamos (`#como-trabajamos`) · Contacto (`#contacto`)
- Botón: **Cuéntanos tu proyecto** (CTA principal)

En móvil se ocultan los enlaces y solo quedan la marca y el botón (sin menú hamburguesa ni JavaScript).

---

## 5. Hero

**Rótulo (encima del título):** Software · Nube · Consultoría

**Título (único `h1`):**
# Software que aguanta el día a día de tu negocio

**Subtítulo:**
En Bujia Tech desarrollamos sistemas a la medida, los publicamos en la nube y los conectamos con el equipo que ya tienes en tu local. Sabemos hacerlo porque lo hacemos: nuestro propio sistema, BujiOps, opera en producción en un taller real.

**Botones:** [Cuéntanos tu proyecto] (principal) · [Ver BujiOps] (secundario)

**Línea de apoyo (debajo de los botones, texto pequeño):**
Platicamos sin compromiso y te decimos con claridad si podemos ayudarte.

---

## 6. Quiénes somos  (`id="quienes-somos"`)

**Título (h2):** Ingeniería que nació en un taller

Bujia Tech es la empresa de software de Ricardo Pérez, ingeniero en sistemas. Ricardo también dirige Bujia Project Music, un taller de reparación y fabricación de guitarras y bajos en Texcoco, Estado de México.

En lugar de acomodar el taller a un sistema genérico, construimos el sistema a la medida del taller: desde que entra un instrumento hasta que el cliente lo recoge y paga. Ese sistema es BujiOps, y hoy cualquier taller de reparación lo puede usar.

Así trabajamos con cada cliente: primero entendemos cómo opera tu negocio y después escribimos código.

[PENDIENTE: foto de Ricardo o del lugar de trabajo, con su texto alternativo. Opcional: decidir si se menciona algo más del equipo; no se pone tamaño de equipo ni años de experiencia hasta que Ricardo lo dé.]

---

## 7. Servicios  (`id="servicios"`)

**Título (h2):** Qué hacemos

**Entrada:** Cuatro formas de ayudarte, y se pueden combinar. Muchas veces un proyecto empieza como consultoría y termina en un sistema publicado.

### 7.1 Desarrollo de software a la medida
Sistemas web hechos para la forma en que ya trabajas, no al revés: control de órdenes, inventarios, cobranza, paneles para tu equipo y páginas para tus clientes.
- Aplicaciones web que funcionan en computadora y en celular
- Sistemas internos con usuarios, roles y sucursales
- Páginas públicas para tus clientes: seguimiento, cotizaciones, registros
- Recibos y etiquetas imprimibles, y mensajes de WhatsApp ya redactados

### 7.2 Nube
Publicamos tu sistema en servidores en la nube, con dominio propio, HTTPS y despliegues automáticos, para que cada mejora llegue a producción sin pasos a mano.
- Contenedores Docker en servidores en la nube
- Despliegue continuo con GitHub Actions
- Almacenamiento de fotos y archivos en la nube
- Dominio, certificados y configuración del servidor

### 7.3 Soluciones híbridas
No todo vive en internet. Conectamos tu sistema en la nube con lo que está físicamente en tu local: impresoras, lectores y equipos que tienen que responder ahí mismo.
- Agentes locales que reciben órdenes desde la nube y las ejecutan en tu equipo
- Impresión de etiquetas y recibos desde el sistema
- Integración con el hardware que ya tienes
- Ejemplo real: en BujiOps, un agente escrito en Rust imprime etiquetas con QR en una Brother QL-800 del taller

### 7.4 Consultoría
Te ayudamos a decidir antes de invertir: qué conviene construir, qué conviene comprar y cómo ordenar lo que ya tienes.
- Diagnóstico de procesos y de los sistemas que ya usas
- Arquitectura y elección de tecnología
- Revisión técnica de proyectos existentes
- Plan por etapas, empezando por lo que más te urge

---

## 8. BujiOps, nuestro producto  (`id="bujiops"`)

**Rótulo:** Producto propio

**Título (h2):** BujiOps: lo construimos, lo publicamos y lo operamos

**Entrada:**
BujiOps nació para administrar Bujia Project Music y hoy es un CRM para cualquier taller de reparación: motos, bicicletas, celulares, instrumentos y más. Es la mejor muestra de lo que podemos construir para ti, porque lo usamos en un taller real.

**Lo que hace (lista):**
- Recepción del equipo en 4 pasos y tablero Kanban por equipo
- Visitas con servicios, refacciones y notas
- Recibos imprimibles y etiquetas con QR
- Directorio de clientes con mensajes de seguimiento por WhatsApp ya redactados
- Página pública donde el cliente ve el avance, sus pagos y su saldo, y califica el servicio
- Página pública de prerregistro y cotización
- Pagos con comprobante y finanzas: caja, gastos fijos y variables, cobranza, mejores clientes y recordatorios
- Usuarios, roles, sucursales y desempeño por técnico

**Cómo está hecho (subtítulo h3: «Lo que hay detrás»):**
- Interfaz en React, Vite y Tailwind; API en NestJS con Prisma y PostgreSQL
- Contenedores Docker en DigitalOcean con Caddy, y despliegue continuo con GitHub Actions
- Fotos y archivos en Google Cloud Storage
- Agente de impresión en Rust conectado a una Brother QL-800

**Nota de precios (texto pequeño):** Planes desde una prueba de $0 hasta el plan Pro. Precios vigentes en bujiops.app.
> Nota editorial: no copiar la tabla de precios aquí para que no se desactualice; la fuente es bujiops.app (hoy: Prueba $0, Solo $299, Taller $499, Pro $1,799 MXN/mes).

**Botón:** [Conocer BujiOps] → `https://bujiops.app/`

**Imagen:** [PENDIENTE: captura de BujiOps. Reutilizar una de las capturas reales del tablero que usa bujiops.app (datos ficticios, nunca de un taller real), en WebP dentro de un marco de ventana. Texto alternativo: «Tablero de BujiOps con las órdenes de un taller organizadas por estado».]

---

## 9. Cómo trabajamos  (`id="como-trabajamos"`)

**Título (h2):** Cómo trabajamos

1. **Platicamos.** Nos cuentas qué necesitas y cómo trabajas hoy. Hacemos preguntas hasta entender el problema real.
2. **Te proponemos.** Recibes por escrito el alcance, las etapas, los tiempos y el costo. Sin letras chiquitas.
3. **Construimos por entregas.** Trabajamos en etapas cortas y ves avances funcionando desde el principio, no hasta el final.
4. **Publicamos y acompañamos.** Dejamos el sistema en línea, te enseñamos a usarlo y seguimos disponibles para ajustes y mejoras.

[PENDIENTE: decidir si la primera plática es sin costo y si hay soporte posterior incluido; si sí, agregarlo a los pasos 1 y 4.]

---

## 10. Contacto  (`id="contacto"`)

**Título (h2):** ¿Tienes un proyecto en mente?

Cuéntanos qué quieres resolver. Si podemos ayudarte, te decimos cómo; si no, también te lo decimos.

**Botones:**
- [Cuéntanos tu proyecto] → WhatsApp (CTA principal, mismo enlace que el hero)
- [Escríbenos un correo] → `mailto:{{CORREO}}?subject=Proyecto%20desde%20el%20sitio`

**Datos visibles:**
- WhatsApp: {{TELEFONO_VISIBLE}}
- Correo: {{CORREO}}
- [PENDIENTE: tiempo de respuesta que se puede cumplir, p. ej. «Respondemos en un día hábil». Si no se decide, esta línea no se publica.]

**Aviso corto (texto pequeño, debajo):** Cuando nos escribes, usamos tus datos solo para responderte y darle seguimiento a tu proyecto. Consulta nuestro [aviso de privacidad](aviso-de-privacidad.html).

---

## 11. Pie de página

- **Bujia Tech** · Software a la medida, nube y consultoría
- Enlaces: [Aviso de privacidad](aviso-de-privacidad.html) · [BujiOps](https://bujiops.app/) · Correo (`mailto:{{CORREO}}`) · WhatsApp (mismo enlace `wa.me` del CTA principal)
- © 2026 Bujia Tech. Hecho en México.
- [PENDIENTE: enlaces a LinkedIn y GitHub de la empresa; no se agregan hasta tener las URL reales.]

---

## 12. Aviso de privacidad (borrador para `aviso-de-privacidad.html`)

> Estructura conforme al artículo 15 de la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP, DOF 20/03/2025). **[PENDIENTE: revisión de un abogado antes de publicar.]**

**Título (h1):** Aviso de privacidad

**Última actualización:** {{FECHA_AVISO}}

**1. Responsable.** {{RESPONSABLE}} («Bujia Tech»), con domicilio en {{DOMICILIO}}, es responsable del tratamiento de tus datos personales. Contacto de privacidad: {{CORREO_PRIVACIDAD}}.

**2. Datos que recabamos.** Cuando nos escribes por WhatsApp o por correo podemos recabar: nombre, teléfono, correo electrónico, nombre de tu empresa o negocio y la información que nos compartas sobre tu proyecto. **No recabamos datos personales sensibles.** Te pedimos no enviarlos.

**3. Finalidades.**
- *Necesarias* (no requieren tu consentimiento porque son para atender lo que nos pides): responder tu mensaje, entender tu proyecto, elaborar propuestas y cotizaciones, y, si nos contratas, prestar y dar seguimiento a los servicios.
- *Adicionales* (requieren tu consentimiento): enviarte información sobre nuestros servicios y productos, incluido BujiOps. Puedes negarte en cualquier momento escribiendo a {{CORREO_PRIVACIDAD}}; negarte no afecta las finalidades necesarias.

**4. Cómo limitar el uso o divulgación de tus datos.** Escríbenos a {{CORREO_PRIVACIDAD}} con el asunto «Limitar uso de datos» y te incluimos en nuestro listado de exclusión.

**5. Transferencias y proveedores.** No vendemos ni compartimos tus datos con terceros para sus propios fines. Solo los comunicamos cuando lo exige la ley o una autoridad competente. Para comunicarnos contigo usamos servicios de terceros (WhatsApp y nuestro proveedor de correo), que tratan la información conforme a sus propios avisos. [PENDIENTE: nombrar al proveedor de correo cuando exista.]

**6. Derechos ARCO.** Tienes derecho a acceder a tus datos, rectificarlos, cancelarlos u oponerte a su tratamiento (derechos ARCO), y a revocar tu consentimiento. Envía tu solicitud a {{CORREO_PRIVACIDAD}} con: tu nombre y un medio para responderte; una identificación oficial (o la de tu representante y el documento que lo acredite); la descripción clara del derecho que quieres ejercer y de los datos involucrados; y cualquier documento que ayude a localizarlos. Te responderemos en los plazos que establece la LFPDPPP. Si consideras que tu derecho no fue atendido, puedes acudir a la Secretaría Anticorrupción y Buen Gobierno.

**7. Cookies y tecnologías de rastreo.** Este sitio no usa cookies, analítica ni herramientas de rastreo. El servicio de alojamiento (GitHub Pages) puede registrar datos técnicos, como la dirección IP, por seguridad y operación.

**8. Cambios a este aviso.** Cualquier cambio se publica en esta misma página, en `https://{{DOMINIO}}/aviso-de-privacidad.html`, con su fecha de actualización.

**Enlace de regreso:** ← Volver al inicio (`./`)

---

## 13. Datos pendientes de contacto e identidad (checklist)

Bujia Tech todavía no tiene estos datos. Mientras falten, el sitio usa los marcadores de la columna derecha y el workflow avisa en cada publicación.

- [ ] **Dominio** (p. ej. `.mx` o `.com`), comprarlo y configurar el DNS para GitHub Pages → `{{DOMINIO}}` (sin `https://` ni `/` final)
- [ ] **Correo con dominio propio** (p. ej. `contacto@{{DOMINIO}}`) y proveedor de correo → `{{CORREO}}`
- [ ] **Correo para privacidad/ARCO** (puede ser el mismo) → `{{CORREO_PRIVACIDAD}}`
- [ ] **WhatsApp Business o teléfono propio de Bujia Tech** (nunca el del taller) → `{{WHATSAPP}}` (formato `52` + 10 dígitos, para `wa.me`) y `{{TELEFONO_VISIBLE}}` (p. ej. `55 1234 5678`)
- [ ] **Responsable para el aviso de privacidad**: razón social y RFC si hay persona moral, o nombre de la persona física con actividad empresarial → `{{RESPONSABLE}}`
- [ ] **Domicilio para el aviso** (fiscal o para recibir notificaciones) → `{{DOMICILIO}}`
- [ ] **Fecha del aviso** al publicarlo → `{{FECHA_AVISO}}`
- [ ] **Revisión legal** del aviso de privacidad
- [ ] **LinkedIn y GitHub de la empresa** (u organización de GitHub) → se agregan al pie cuando existan
- [ ] **Logo y paleta de Bujia Tech**. Mientras no existan, el sitio usa la marca en texto y una paleta provisional heredada de BujiOps (slate + ámbar, la «chispa» de la bujía), definida en variables CSS para cambiarla en un solo lugar
- [ ] **Foto** para «Quiénes somos» y **captura de BujiOps** para su sección
- [ ] **Decisiones de copy**: ¿primera plática sin costo?, ¿soporte posterior incluido?, tiempo de respuesta
- [ ] **Formulario de contacto: recomendación → no usar formulario en la v1.** WhatsApp (`wa.me`) + `mailto:` funcionan en un sitio estático sin JavaScript, sin terceros adicionales y sin tocar el aviso de privacidad. **Formspree** (o similar) sí funciona en GitHub Pages, pero agrega un proveedor que recibe datos personales (hay que nombrarlo en el aviso), depende de un plan gratuito con límites, requiere filtro anti‑spam y suma una petición externa. Conviene reconsiderarlo solo si el `mailto:` no genera contactos o si hace falta pedir datos estructurados (presupuesto, tipo de proyecto).
