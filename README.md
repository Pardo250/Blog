# El poder de las notas: impactos en la música

Blog académico sobre el impacto de la música en las personas y en la sociedad, con una sección de reseñas dedicada al rock en español.

**Ver el blog:** https://pardo250.github.io/Blog/

## Tabla de contenido

- [Sobre el blog](#sobre-el-blog)
- [Contenido](#contenido)
- [Autores](#autores)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Diseño](#diseño)
- [Cómo verlo en tu computador](#cómo-verlo-en-tu-computador)
- [Cómo editar el contenido](#cómo-editar-el-contenido)
- [Publicación](#publicación)
- [Pendientes](#pendientes)
- [Referencias](#referencias)

## Sobre el blog

A lo largo de la historia, la música ha ejercido un rol fundamental en la configuración de la realidad social. Este blog explora cómo la música impacta en los más diversos ámbitos del ser humano: la guerra y la memoria histórica, la transformación social en comunidades vulnerables, el desarrollo del cerebro y el sentido de pertenencia.

Cada entrada reúne textos cortos escritos por los integrantes del grupo a partir de artículos académicos, y cada texto va firmado con las iniciales de quien lo escribió.

## Contenido

| Sección | De qué trata |
| --- | --- |
| **Portada** | Párrafo introductorio del blog y firmas de los autores. |
| **Entrada 1 — Frases para empezar** | Tres citas textuales de los referentes estudiados, una por integrante. |
| **Pregunta de interacción** | "¿Qué canción los ha marcado? O bien, ¿cuál es su canción favorita en este momento?" |
| **Entrada 2 — Guerra, comunidad y cerebro** | La música en la guerra (MM), la música como transformación social (JP) y el impacto de la música en el cerebro (ARP). |
| **Entrada 3 — Entrada libre** | Música y cohesión de grupo (ARP), "Te quiero dijiste" (MM) y "Más que notas: la música como lugar de pertenencia" (JP). |
| **Reseñas** | Una reseña por integrante sobre una banda o cantante de rock en español. |
| **Referencias** | Bibliografía en formato APA. |

## Autores

Los textos están firmados con iniciales. Cada autor tiene un color propio en el blog:

| Firma | Color |
| --- | --- |
| **MM** | Rosa |
| **JP** | Amarillo |
| **ARP** | Azul |

## Estructura del proyecto

```
Blog/
├── index.html   Todo el blog: contenido, estilos y estructura en un solo archivo
└── README.md    Este documento
```

El blog es una sola página HTML sin dependencias que instalar ni pasos de compilación. Lo único externo son las tipografías, que se cargan desde Google Fonts.

Dentro de `index.html` el orden es:

1. `<head>`: título, descripción y enlace a las tipografías.
2. `<style>`: todos los estilos. Los colores y tipografías están definidos como variables al inicio, en el bloque `:root`.
3. `<body>`: barra superior, portada, franja de bandas y luego una `<section>` por cada parte del blog (`#entrada-1`, `#pregunta`, `#entrada-2`, `#entrada-3`, `#resenas`, `#referencias`).

## Diseño

El blog está pensado como un cartel de concierto impreso a tres tintas.

- **Colores:** rosa, amarillo y azul sobre un fondo claro azulado. Tiene versión clara y oscura, y se adapta sola al tema del dispositivo.
- **Tipografías:**
  - *Anton* para titulares.
  - *Source Serif 4* para el texto de lectura.
  - *DM Mono* para etiquetas y citas de fuente.
- **Detalles propios del tema:** un vinilo que gira en la portada, una franja con bandas de rock en español y tarjetas de reseña con forma de casete.
- **Adaptable:** funciona en computador y en celular. En pantallas pequeñas las columnas se apilan.
- **Accesibilidad:** la animación del vinilo se desactiva si el dispositivo tiene activada la opción de reducir movimiento.

Para cambiar un color en todo el blog basta con editar su variable en `:root` (por ejemplo `--accent` para el rosa). Hay que cambiarlo también en los dos bloques del tema oscuro que están justo debajo.

## Cómo verlo en tu computador

1. Descarga o clona el repositorio:
   ```bash
   git clone https://github.com/Pardo250/Blog.git
   ```
2. Abre `index.html` con doble clic. Se abre en el navegador, sin instalar nada.

Se necesita conexión a internet para que carguen las tipografías. Sin conexión el blog funciona igual, pero con las fuentes del sistema.

## Cómo editar el contenido

Todo se edita en `index.html` con cualquier editor de texto o de código.

### Agregar un texto a una entrada

Cada texto es un bloque `<article class="piece">`. Copia este bloque dentro de la entrada que corresponda y cambia la firma, el título y los párrafos:

```html
<article class="piece">
  <div class="rail"><span class="sig mm">MM</span></div>
  <div class="text">
    <h3>Título del texto</h3>
    <p>Primer párrafo.</p>
    <p>Segundo párrafo.</p>
  </div>
</article>
```

La clase de la firma define el color: `sig mm`, `sig jp` o `sig arp`.

### Agregar una entrada nueva

1. Copia una `<section class="entry">` completa y pégala antes de la sección de reseñas.
2. Cámbiale el `id` (por ejemplo `id="entrada-4"`), la etiqueta y el título del encabezado.
3. Agrega el enlace en el menú de la barra superior:
   ```html
   <a href="#entrada-4">Entrada 4</a>
   ```

Las secciones alternan fondo: las que llevan `class="entry alt"` tienen un fondo más oscuro.

### Llenar una reseña

Cada reseña es un `<article class="tape">` dentro de la sección `#resenas`. Reemplaza el título "Banda o artista por definir" por el nombre de la banda o cantante, y sustituye la lista `<dl>` y la etiqueta "Pendiente" por los párrafos de la reseña.

### Marcar algo como pendiente

```html
<span class="pending">Pendiente</span>
```

### Agregar una referencia

Agrega un `<li>` a la lista `<ul class="refs">`, en orden alfabético y en formato APA. El nombre de la revista y el volumen van dentro de `<em>`.

## Publicación

El blog está publicado con **GitHub Pages** desde la rama `main`, carpeta raíz.

Para publicar un cambio:

```bash
git add index.html
git commit -m "Describe aquí el cambio"
git push
```

Uno o dos minutos después del `push`, el cambio aparece en https://pardo250.github.io/Blog/. Si no se ve, recarga la página con `Ctrl + F5`.

La configuración está en **Settings → Pages** del repositorio.

## Pendientes

- [ ] Continuación del texto "Te quiero dijiste" de MM en la Entrada 3.
- [ ] Reseñas de rock en español de MM, JP y ARP.
- [ ] Referencia de Meza et al. (2024), citada en la Entrada 3.
- [ ] Imágenes para la portada, las entradas y las reseñas.
- [ ] Entradas restantes.

## Referencias

Fernández Ampié, G. (2024). Música en la guerra: los mensajes de las canciones "contras." *Meridional: Revista Chilena de Estudios Latinoamericanos, 23*, 205–234. https://doi.org/10.5354/0719-4862.2024.76349

Lara Figueroa, E. (2025). El poder transformador de la música en niños y jóvenes: La práctica musical grupal como agente de cambio. *AULA Revista de Humanidades y Ciencias Sociales, 72*(1), (5). https://doi.org/10.33413/aulahcs.2025.71i1.396

Solís, K. S., y Torres, S. P. (2025). Impactos de la música electrónica en el cerebro joven. *Revista Paraguaya de Educación, 14*(2), 141-154.
