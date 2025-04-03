title: "Un paso adelante"
description: "Recursos para estudiantes de 6º de Derecho en Uruguay"
baseurl: ""
url: "https://tuusuario.github.io"
github_username: "tuusuario"

# Configuración de Jekyll
theme: minima
plugins:
  - jekyll-feed
  - jekyll-seo-tag
  - jekyll-sitemap
  - jekyll-paginate
  - jekyll-archives
  - jekyll-search

# Configuración de la paginación
paginate: 5
paginate_path: "/page:num/"

# Configuración de Disqus para comentarios
disqus:
  shortname: "tublog"

# Datos de contacto
contact:
  email: "juangabrielsilvera00@gmail.com"

# Estructura del blog
collections:
  materias:
    output: true
    permalink: "/materias/:name/"
  unidades:
    output: true
    permalink: "/unidades/:name/"
  temas:
    output: true
    permalink: "/temas/:name/"

# Barra de búsqueda
search: true

# Archivos y diseño
include:
  - _layouts
  - _includes
  - assets

# Página principal (index.html)
---
layout: default
title: Inicio
---

<h1>Bienvenidos a Un paso adelante</h1>
<p>Aquí encontrarás toda la información relevante para estudiantes de 6º de Derecho en Uruguay.</p>
<input type="text" id="search" placeholder="Buscar temas...">
<div id="results"></div>

<h2>Materias</h2>
<ul>
  {% for materia in site.materias %}
    <li><a href="{{ materia.url }}">{{ materia.title }}</a></li>
  {% endfor %}
</ul>

# Plantilla para publicaciones (_layouts/post.html)
---
layout: default
---

<h1>{{ page.title }}</h1>
<img src="{{ page.image }}" alt="{{ page.title }}">
<p>{{ page.description }}</p>
<div>{{ content }}</div>

<h3>Fuentes y Documentos</h3>
<ul>
  {% for fuente in page.fuentes %}
    <li><a href="{{ fuente.link }}">{{ fuente.nombre }}</a></li>
  {% endfor %}
</ul>

<h3>Comentarios</h3>
{% if site.disqus.shortname %}
  {% include disqus_comments.html %}
{% endif %}

# Barra de búsqueda (_includes/search.html)
<script>
document.getElementById("search").addEventListener("keyup", function() {
  let query = this.value.toLowerCase();
  let results = document.getElementById("results");
  results.innerHTML = "";
  site.temas.forEach(function(tema) {
    if (tema.title.toLowerCase().includes(query)) {
      let item = document.createElement("div");
      item.innerHTML = `<a href="${tema.url}">${tema.title}</a>`;
      results.appendChild(item);
    }
  });
});
</script>

# Ejemplo de publicación (_temas/batllismo.md)
---
title: "El Batllismo"
image: "/assets/images/batllismo.jpg"
description: "Explicación sobre el Batllismo en la historia de Uruguay."
fuentes:
  - nombre: "Historia del Uruguay"
    link: "https://historiauruguay.com"
  - nombre: "Documento PDF"
    link: "/assets/docs/batllismo.pdf"
---

<p>El Batllismo fue una corriente política liderada por José Batlle y Ordóñez...</p>

# Contacto (contacto.md)
---
title: "Contacto"
---
<h1>Contacto</h1>
<p>Si necesitás información, escribime a <a href="mailto:juangabrielsilvera00@gmail.com">juangabrielsilvera00@gmail.com</a></p>
