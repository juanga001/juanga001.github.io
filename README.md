<!DOCTYPE html>
<html>
<head>
    <title>Mi página de noticias</title>
    <style>
        body {
            font-family: sans-serif;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 20px;
        }

        h1 {
            margin: 0;
        }

        #contenido {
            padding: 20px;
        }

        .noticia {
            margin-bottom: 20px;
            border: 1px solid #ccc;
            padding: 10px;
        }

        .noticia img {
            max-width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Mi página de noticias</h1>
    </header>

    <div id="contenido">
        <div class="noticia">
            <h2>Nueva noticia</h2>
            <p>Esta es una noticia importante que quiero compartir con ustedes.</p>
            <img src="imagenes/imagen-de-la-noticia.jpg" alt="Imagen de la noticia">
            <a href="documento.pdf">Descargar documento</a>
        </div>

        <div class="noticia">
            <h2>Otra noticia</h2>
            <p>Aquí hay otra noticia interesante.</p>
            <img src="imagenes/otra-imagen.jpg" alt="Otra imagen">
        </div>
    </div>
</body>
</html>
