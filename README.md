# 📁 RASTRO-USER

**Herramienta OSINT de pivote por Username / Email — Redes globales + plataformas españolas**

🔗 **Demo en vivo:** [https://s3gad3.github.io/rastro-user/](https://s3gad3.github.io/rastro-user/)

Complemento de [RASTRO-GH](https://s3gad3.github.io/rastro-gh/) dentro del mismo kit de herramientas de ciberinteligencia. Mientras RASTRO-GH pivota desde GitHub hacia emails, **RASTRO-USER** parte de un **username** o un **email** conocidos y genera automáticamente los enlaces de comprobación en las plataformas más usadas en España y a nivel global.

---

## ⚙️ Características

- **Archivo único, sin backend.** Todo el código (HTML + CSS + JS) vive en un solo `.html`. No hay servidor, no hay claves de API, no se envía ni almacena ningún dato del usuario. Todo ocurre en el navegador.
- **Dos modos de búsqueda:**
  - **Username** → genera enlaces a ~21 plataformas agrupadas por categoría (redes globales, foros españoles, gaming/streaming, compraventa, menciones cruzadas).
  - **Email** → mantiene el pivote clásico (Google, DuckDuckGo, GitHub código/commits, Gravatar, Hunter.io, Epieos, Have I Been Pwned) y añade dorks automáticos por cada foro español y por Instagram/Facebook.
- **Enlace directo vs. dork — diferenciados visualmente:**
  - 🔵 **Azul** = URL de perfil construida y verificada directamente a partir del username (p. ej. `mediavida.com/id/USUARIO`).
  - 🟢 **Verde** = dork de Google (`site:dominio.com "término"`) usado cuando la plataforma **no** ofrece un patrón de perfil fiable a partir del username (Wallapop, Milanuncios, Burbuja.info, Vandal, 3DJuegos, ElOtroLado, Coches.net).
- **Gravatar con verificación real:** hash MD5 calculado en el propio navegador (implementación propia, sin librerías), comprobación automática de si existe avatar público (`onload`/`onerror` sobre la imagen) y descarga directa vía `fetch` → `Blob`.
- **Modal de imagen reutilizable:** vista ampliada + descarga, igual que en RASTRO-GH.
- **Categorías desplegables (`<details>`)** con grid de botones grandes estilo sello, para no saturar la vista con las ~25+ opciones disponibles.
- **Estética "expediente":** carpeta de papel kraft, cinta adhesiva, textura de papel, tipografía Special Elite (títulos) + monoespaciada (cuerpo), botones con sombra desplazada tipo sello de goma — mismo lenguaje visual que RASTRO-GH.

---

## 🌍 Plataformas cubiertas

**Redes globales:** Instagram, X/Twitter, Facebook, TikTok, LinkedIn, YouTube, Telegram

**Foros España — enlace directo:** Forocoches, Mediavida, Menéame

**Foros España — vía dork:** Burbuja.info, Vandal, 3DJuegos, ElOtroLado, Coches.net

**Compraventa — vía dork:** Wallapop, Milanuncios

**Gaming / Streaming:** Twitch, Kick, Steam, Spotify

**Email — pivotes adicionales:** Google, DuckDuckGo, GitHub (código y commits), Gravatar, Hunter.io, Epieos, Have I Been Pwned, dorks por cada foro español, dorks Instagram/Facebook

> Los patrones de URL de los foros españoles se verificaron manualmente antes de implementarlos (varios usan vBulletin, XenForo o motores propios con esquemas no estándar). Donde no se pudo confirmar un patrón de perfil fiable, se optó por un dork de Google en lugar de un enlace potencialmente roto.

---

## 🚀 Uso

1. Abre `index.html` en cualquier navegador (o entra en la [demo en vivo](https://s3gad3.github.io/rastro-user/)).
2. Elige la pestaña **Username** o **Email**.
3. Introduce el dato objetivo y pulsa **Generar Pivotes**.
4. Despliega las categorías y pulsa cualquier botón para abrir la comprobación en una pestaña nueva.
5. En la pestaña Email, revisa automáticamente si existe avatar de Gravatar; si existe, puedes verlo ampliado y descargarlo.

No requiere instalación, dependencias de build ni configuración. Es un sitio estático — puede alojarse en GitHub Pages, abrirse localmente con doble clic, o integrarse en cualquier flujo de trabajo interno.

---

## 🛠️ Stack técnico

- HTML5 + CSS3 (sin frameworks)
- JavaScript vanilla (sin librerías externas)
- Implementación propia de MD5 (dominio público) para Gravatar
- Google Fonts (Special Elite, Courier Prime) vía CDN — única dependencia externa, solo tipografía

---

## ⚠️ Uso previsto

Herramienta de **uso interno autorizado** para investigación de ciberinteligencia y cibercrimen. Únicamente construye y abre enlaces a información pública o motores de búsqueda públicos; no accede, automatiza scraping ni almacena datos de terceros. El investigador es responsable de verificar visualmente cada resultado y de operar dentro del marco legal aplicable a su investigación.

---

## 🔗 Proyectos relacionados

- [RASTRO-GH](https://s3gad3.github.io/rastro-gh/) — pivote OSINT desde GitHub hacia emails y perfiles asociados.
