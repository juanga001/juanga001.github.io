<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Foro Anónimo</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #f9f9f9;
            color: #333;
        }
        header {
            background: #2c3e50;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        header h1 {
            margin: 0;
            font-size: 2.5em;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        form {
            margin-bottom: 20px;
        }
        input, textarea, button {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 1em;
        }
        button {
            background: #34495e;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background: #2c3e50;
        }
        .post {
            background: #f1f1f1;
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 5px;
        }
        .post p {
            margin: 0;
        }
        .post .author {
            font-weight: bold;
            color: #34495e;
        }
        footer {
            text-align: center;
            margin-top: 20px;
            font-size: 0.9em;
            color: #777;
        }
    </style>
</head>
<body>
    <header>
        <h1>Foro Anónimo</h1>
    </header>

    <div class="container">
        <h2>Publica un mensaje</h2>
        <form id="postForm">
            <input type="text" id="username" placeholder="Tu nombre (opcional)" />
            <textarea id="message" placeholder="Escribe tu mensaje..." required></textarea>
            <label>
                <input type="checkbox" id="anonymous" /> Publicar de forma anónima
            </label>
            <button type="submit">Publicar</button>
        </form>

        <h2>Mensajes</h2>
        <div id="posts"></div>
    </div>

    <footer>
        © 2025 Foro Anónimo
    </footer>

    <script>
        // Simulación de publicaciones (en un proyecto real, esto vendría de una base de datos)
        let posts = [];

        const postForm = document.getElementById('postForm');
        const postsContainer = document.getElementById('posts');

        postForm.addEventListener('submit', function (e) {
            e.preventDefault();

            const username = document.getElementById('username').value.trim();
            const message = document.getElementById('message').value.trim();
            const anonymous = document.getElementById('anonymous').checked;

            if (!message) return;

            const author = anonymous ? 'Anónimo' : username || 'Usuario sin nombre';
            const newPost = { author, message, timestamp: new Date().toLocaleString() };

            // Agregar el mensaje al array (en un proyecto real, enviarías esto al backend)
            posts.push(newPost);

            // Limpiar el formulario
            postForm.reset();

            // Actualizar la lista de mensajes
            renderPosts();
        });

        function renderPosts() {
            postsContainer.innerHTML = '';
            posts.forEach(post => {
                const postElement = document.createElement('div');
                postElement.classList.add('post');
                postElement.innerHTML = `
                    <p><span class="author">${post.author}</span> (${post.timestamp})</p>
                    <p>${post.message}</p>
                `;
                postsContainer.appendChild(postElement);
            });
        }

        // Cargar mensajes iniciales
        renderPosts();
    </script>
</body>
</html>
