# CARTA — Proyecto web «Cafe Barista»

**Materia:** GIT y GitHub
**Alumno:** David (Deividcodv)
**Correo:** davivasquez02@gmail.com
**Repositorio:** https://github.com/Deividcodv/Cafe-Barista
**Fecha:** 4 de octubre de 2026

---

## 1. Introducción

La cafetería **Cafe Barista** necesita una presencia en internet sencilla que le permita mostrar su carta de productos, sus horarios de atención y sus datos de contacto. El presente proyecto consistió en construir esa página web con HTML y CSS, y en publicarla en GitHub siguiendo un flujo de trabajo profesional con Git: control de versiones, ramas de trabajo, *commits* pequeños y descriptivos, *push* al repositorio remoto, Pull Requests y *merge* a la rama principal `master`.

La elección de GitHub como plataforma no es casual: el repositorio funciona como bitácora digital del proyecto. Cada cambio quedó registrado con su autor, su fecha y su motivo, lo que permite auditar la evolución del sitio y volver a cualquier versión anterior. Además, el uso de ramas y Pull Requests permite trabajar en features sin romper la versión que los usuarios ya están viendo, que es exactamente el flujo que sigue un equipo real de desarrollo web.

**Objetivo general:** desarrollar y publicar la página de Cafe Barista en GitHub aplicando un flujo de trabajo basado en ramas, *commits* y Pull Requests.

**Objetivos específicos:**

1. Crear la estructura del proyecto con `index.html` y `estilos.css`.
2. Inicializar el repositorio de Git y registrar un primer *commit*.
3. Crear el repositorio en GitHub y subir el proyecto.
4. Agregar una sección de promociones en una rama `promociones`, con al menos dos *commits*, y fusionarla mediante un Pull Request.
5. Realizar dos mejoras visuales en una rama `mejorar-diseño`, repetir el flujo *commit → push → PR → merge*.
6. Documentar todo el proceso con evidencia gráfica.

**Justificación de las herramientas.** Se eligió HTML5 semántico y CSS3 puro porque no requieren instalación, funcionan en cualquier navegador y son los estándares para páginas estáticas. Se descartó un framework como Bootstrap para demostrar el uso propio de `flexbox`, `grid`, variables CSS y *media queries*, que son los recursos que una cafetería pequeña necesitaría mantener por sí misma.

---

## 2. Contenido

### 2.1 Estructura del proyecto

```
Cafe-Barista/
├── index.html        (215 líneas) — estructura y contenido de la página
├── estilos.css       (545 líneas) — diseño, responsividad y animaciones
├── capturas/         (22 imágenes)  — evidencia gráfica del proceso
├── CARTA.md          — este documento
├── CARTA.pdf         — versión impresa de la carta
└── CARTA.html        — versión maquetada usada para generar el PDF
```

### 2.2 Contenido de la página

La página está organizada en cinco bloques, navegables desde el menú superior:

| Sección | Contenido |
|---|---|
| **Hero** | Nombre de la cafetería, eslogan y dos botones de llamada a la acción (Ver productos / Cómo llegar). |
| **Productos** | Seis artículos con nombre, descripción y precio: Espresso, Capuchino, Latte, Matcha Latte, Croissant y Brownie. |
| **Promociones** | Tres tarjetas de oferta: 2×1 en café filtrado, Combo Barista Breakfast y 15 % en grupos de 6. |
| **Horarios** | Tabla de lunes a domingo con el horario de apertura y cierre, más un bloque informativo sobre los descuentos de las mañanas. |
| **Contacto** | Dirección, teléfono, correo electrónico y redes sociales, además del pie de página con los datos de la cafetería. |

Aspectos técnicos del HTML: se declara el atributo `lang="es"`, se emplean elementos semánticos (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`), cada sección tiene su `id` para poder enlazarla desde el menú, y las imágenes son SVG o emoji decorativos con `aria-hidden` para no interferir con los lectores de pantalla.

### 2.3 Decisiones técnicas del CSS

- **Variables CSS** (`:root`) para centralizar colores, radios, sombras y tipografías. Cambiar la identidad visual del sitio requiere modificar una sola línea.
- **`grid` y `flexbox`** para la distribución: rejilla de productos y contacto, barra de horarios en dos columnas y hero en dos columnas.
- **Responsividad** con dos `media queries` (900 px y 640 px): en móvil las columnas se apilan, el menú se centra y la ilustración del hero se oculta.
- **Sin dependencias externas.** Las tipografías son pilas del sistema y todas las ilustraciones son SVG o CSS, de modo que la página se ve igual sin conexión a internet.
- **Animaciones con criterio**: transiciones de 0.25 s, elevación de tarjetas al pasar el cursor y subrayado del menú que crece desde el centro.
- **Accesibilidad**: `:focus-visible` para navegación por teclado, `prefers-reduced-motion` para respetar a quien desactivó las animaciones y `scroll-margin-top` para que el menú fijo no tape los títulos.

### 2.4 Flujo de trabajo con Git

El trabajo se organizó en cuatro momentos, todos sobre la rama `master`:

| Paso | Acción | Resultado |
|---|---|---|
| 1 | `git init -b master` + primer `commit` | Repositorio local con `a43f8dd` |
| 2 | `gh repo create --public --push` | Repositorio `Deividcodv/Cafe-Barista` |
| 3 | Rama `promociones` → 2 `commit` → *push* → PR #1 → *merge* | Sección de promociones en producción |
| 4 | Rama `mejorar-diseño` → 2 `commit` → *push* → PR #2 → *merge* | Dos mejoras visuales en producción |

Las tres ramas quedaron publicadas en GitHub: `master` (versión final), `promociones` (con la sección de ofertas) y `mejorar-diseño` (con las mejoras de diseño). Se conservaron después del *merge* para que quede evidencia del proceso.

### 2.5 Historial de commits

```
*   0fca0b6 Merge pull request #2 from Deividcodv/mejorar-diseno
|\
| * cc66cff style: agrega animaciones, transiciones y mejoras de accesibilidad
| * ce05d69 style: renueva la tipografia, la paleta y el hero a dos columnas
|/
*   7ebb1ac Merge pull request #1 from Deividcodv/promociones
|\
| * 2812a2d style: estiliza las tarjetas de promociones y aclara sus condiciones en horarios
| * 0b8c86f feat: agrega la seccion de promociones al inicio de la pagina
|/
* a43f8dd chore: inicializa el proyecto Cafe Barista con index.html y estilos.css
```

| Commit | Rama | Descripción |
|---|---|---|
| `a43f8dd` | master | Commit inicial: `index.html` y `estilos.css` |
| `0b8c86f` | promociones | Sección de promociones en el HTML (3 ofertas + enlace en el menú) |
| `2812a2d` | promociones | Estilos de las tarjetas de promociones y nota de no acumulabilidad |
| `7ebb1ac` | master | **Merge del PR #1** |
| `ce05d69` | mejorar-diseño | Mejora 1: tipografía serif, paleta cálida y hero a dos columnas |
| `cc66cff` | mejorar-diseño | Mejora 2: animaciones, transiciones y accesibilidad |
| `0fca0b6` | master | **Merge del PR #2** |

Los mensajes siguen la convención de *Conventional Commits* (`feat:`, `style:`, `chore:`), lo que permite saber de un vistazo si un cambio agrega funcionalidad, modifica estilos o configura el proyecto.

### 2.6 Pull Requests

| PR | Título | Rama origen | Cambios | Estado |
|---|---|---|---|---|
| [#1](https://github.com/Deividcodv/Cafe-Barista/pull/1) | feat: agrega la seccion de promociones | `promociones` | 64 líneas agregadas, 2 eliminadas, 2 archivos | **Fusionado** el 04/10/2026 |
| [#2](https://github.com/Deividcodv/Cafe-Barista/pull/2) | style: dos mejoras visuales para la pagina | `mejorar-diseño` | 203 líneas agregadas, 39 eliminadas, 1 archivo | **Fusionado** el 04/10/2026 |

Cada Pull Request se creó con `gh pr create` incluyendo una descripción con el detalle de los cambios, se verificó con `gh pr view` que GitHub lo marcaba como `MERGEABLE` (sin conflictos) y se integró con `gh pr merge --merge`, que genera un *commit* de fusión y conserva el historial completo de la rama.

---

## 3. Capturas de pantalla

### 3.1 La página web

**Figura 1. Vista completa de la página en escritorio (1351 × 3665 px).**
Se observan las cinco secciones en orden: hero, productos, promociones, horarios, contacto y pie de página.

![Vista completa del sitio](capturas/01-sitio-completo-escritorio.png)

**Figura 2. Cabecera y hero.** El menú fijo con cuatro enlaces, el logotipo con SVG de taza, el eslogan y los dos botones de llamada a la acción, junto a la ilustración de la taza que en la rama `mejorar-diseño` pasó a estar en una columna propia.

![Cabecera y hero](capturas/02-sitio-hero.png)

**Figura 3. Sección de productos.** Rejilla de seis tarjetas con icono, nombre, descripción y precio.

![Sección de productos](capturas/03-sitio-productos.png)

**Figura 4. Sección de promociones.** Las tres ofertas agregadas en el PR #1, con su etiqueta superior y el precio destacado en color de acento.

![Sección de promociones](capturas/04-sitio-promociones.png)

**Figura 5. Sección de horarios.** Tabla de lunes a domingo con franjas alternas y, al lado, el bloque informativo del descuento de mañanas.

![Sección de horarios](capturas/05-sitio-horarios.png)

**Figura 6. Sección de contacto y pie de página.** Dirección, teléfono, correo y redes sociales.

![Sección de contacto y pie](capturas/06-sitio-contacto-y-pie.png)

**Figura 7. Vista en móvil (390 px de ancho).** Todas las columnas se apilan en una sola, el menú se centra y la ilustración del hero se oculta: así se comporta la página en un teléfono.

![Vista móvil completa](capturas/07-sitio-movil-390px.png)

**Figura 8. Promociones en móvil.** Detalle de las tarjetas de ofertas apiladas en una columna, resultado de la regla `@media` de 640 px.

![Promociones en móvil](capturas/08-sitio-movil-promociones.png)

### 3.2 El repositorio en GitHub

**Figura 9. Portada del repositorio** `Deividcodv/Cafe-Barista`, creado como público desde la terminal con `gh repo create`.

![Portada del repositorio](capturas/09-github-portada.png)

**Figura 10. Historial de commits de `master`.** Se ven los siete commits, incluidos los dos *merge* de los Pull Requests.

![Historial de commits](capturas/10-github-commits-master.png)

**Figura 11. Lista de ramas.** Las tres ramas del proyecto: `master`, `mejorar-diseño` y `promociones`.

![Lista de ramas](capturas/11-github-ramas.png)

### 3.3 Pull Request #1 — Secciones de promociones

**Figura 12. PR #1 en conversación.** Título, descripción de los cambios, lista de *commits* y el indicador de que fue fusionado a `master`.

![PR #1 conversación](capturas/12-github-pr1-promociones.png)

**Figura 13. PR #1, archivos modificados.** El diff de `index.html` y `estilos.css` con las líneas agregadas en verde.

![PR #1 archivos](capturas/13-github-pr1-archivos.png)

### 3.4 Pull Request #2 — Mejoras de diseño

**Figura 14. PR #2 en conversación.** Detalle de las dos mejoras visuales y de accesibilidad aplicadas.

![PR #2 conversación](capturas/14-github-pr2-diseno.png)

**Figura 15. PR #2, archivos modificados.** Diff completo de `estilos.css` (203 líneas agregadas, 39 eliminadas).

![PR #2 archivos](capturas/15-github-pr2-archivos.png)

**Figura 16. Commit de fusión del PR #2** (`0fca0b6`), que incorpora a `master` los dos commits de la rama `mejorar-diseño`.

![Commit de fusión](capturas/16-github-commit-merge.png)

### 3.5 Evidencia de la terminal

**Figura 17. Inicialización del repositorio y commit inicial.** `git init -b master`, `git add .` y el primer `commit` que crea `index.html` y `estilos.css`.

![Terminal: init y commit](capturas/17-terminal-1-init-y-commit.png)

**Figura 18. Creación del repositorio en GitHub.** `gh repo create --public --source=. --remote=origin --push` y la rama `master` siguiendo al remoto.

![Terminal: creación del repo](capturas/18-terminal-2-crear-repo-github.png)

**Figura 19. Rama `promociones`.** `git checkout -b promociones`, los dos *commits* de la sección y el `push` de la rama.

![Terminal: rama promociones](capturas/19-terminal-3-rama-promociones.png)

**Figura 20. Pull Request #1 y su fusión.** Creación del PR, verificación `MERGEABLE`, `gh pr merge 1 --merge` y el grafo de `master` después del *merge*.

![Terminal: PR #1 y merge](capturas/20-terminal-4-pr1-merge.png)

**Figura 21. Rama `mejorar-diseño`.** Los dos *commits* de mejoras visuales, el `push` y la creación del PR #2.

![Terminal: rama mejorar-diseño](capturas/21-terminal-5-rama-mejorar-diseno.png)

**Figura 22. Pull Request #2, fusión y estado final.** Fusión, `git pull` de `master`, grafo completo del proyecto y listado de ramas locales y remotas.

![Terminal: PR #2 y estado final](capturas/22-terminal-6-pr2-merge-y-estado-final.png)

---

## 4. Conclusión

El proyecto se completó con éxito y cumple los seis objetivos propuestos. La página de **Cafe Barista** está publicada y accesible en abierto en https://github.com/Deividcodv/Cafe-Barista, muestra los productos con sus precios, los horarios de toda la semana, las promociones vigentes y los datos de contacto, y funciona correctamente tanto en computadora como en teléfono.

Lo que más aprendí fue la diferencia entre «guardar archivos» y «versionar un proyecto». Commitear con mensajes descriptivos y separados en cambios pequeños hace que el historial se lea solo: cualquiera puede entender qué se hizo, cuándo y por qué. Crear un proyecto directamente sobre `master` habría funcionado igual, pero cualquier error había que deshacerlo a mano; con ramas y Pull Requests el error queda aislado, se revisa antes de integrar y `master` siempre tuvo una versión que funcionaba.

También comprobó que GitHub sirve como algo más que un alojamiento: el Pull Request funciona como un lugar donde se documenta y se revisa el trabajo antes de publicarlo, y las ramas permiten mantener varias líneas de trabajo en paralelo.

Como mejora futura, el paso natural sería convertir el sitio en una página dinámica (por ejemplo con JavaScript o un CMS) para que la cafetería pueda actualizar sus promociones y productos sin tocar el código. También se podrían agregar más imágenes reales, una sección de reseñas de clientes y una versión en el menú que mida el tamaño de cada producto.

---

*Documento generado el 4 de octubre de 2026. Repositorio: https://github.com/Deividcodv/Cafe-Barista*