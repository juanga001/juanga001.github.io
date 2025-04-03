<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Todo Lo Que Quieras Saber</title>
    <style>
        /* Estilos básicos */
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
        header p {
            font-size: 1.2em;
            margin-top: 5px;
        }
        .search-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 20px 0;
        }
        .search-container input[type="text"] {
            width: 60%;
            padding: 10px;
            font-size: 1.2em;
            border: 2px solid #34495e;
            border-radius: 5px 0 0 5px;
        }
        .search-container button {
            padding: 10px 20px;
            font-size: 1.2em;
            background: #34495e;
            color: white;
            border: none;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
        }
        .search-container button:hover {
            background: #2c3e50;
        }
        .results {
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 20px;
        }
        .result-item {
            background: white;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        .result-item h3 {
            margin: 0 0 10px;
            color: #2c3e50;
        }
        .result-item p {
            line-height: 1.6;
        }
        .result-item .source {
            font-size: 0.9em;
            color: #777;
        }
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px 0;
            margin-top: 30px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Todo Lo Que Quieras Saber</h1>
        <p>Información verificada y confiable</p>
    </header>

    <div class="search-container">
        <input type="text" id="searchInput" placeholder="Escribe lo que quieres saber...">
        <button onclick="buscar()">Buscar</button>
    </div>

    <div class="results" id="results">
        <!-- Los resultados aparecerán aquí -->
    </div>

    <footer>
        <p>Contacto: <a href="mailto:info@todoquesabes.com" style="color: #3498db;">info@todoquesabes.com</a></p>
        <p>© 2025 Todo Lo Que Quieras Saber</p>
    </footer>

    <script>
        // Simulación de una base de datos con información verificada
        const database = [
            {
                titulo: "¿Es cierto que el cambio climático afecta a los océanos?",
                contenido: "Sí, el cambio climático provoca el aumento del nivel del mar, la acidificación de los océanos y cambios en los patrones de corrientes marinas.",
                fuente: "https://www.ipcc.ch"
            },
            {
                titulo: "¿La vacuna contra el COVID-19 contiene microchips?",
                contenido: "No, esta afirmación es falsa. Las vacunas contra el COVID-19 están compuestas principalmente de componentes biológicos y no contienen microchips.",
                fuente: "https://www.who.int"
            },
            {
                titulo: "¿El agua hierve a 100°C en cualquier lugar?",
                contenido: "No, el punto de ebullición del agua depende de la presión atmosférica. A mayor altitud, el agua hierve a temperaturas más bajas.",
                fuente: "https://www.science.org"
            },
            {
                titulo: "¿Es seguro usar contraseñas comunes?",
                contenido: "No, las contraseñas comunes son fáciles de adivinar. Usa contraseñas únicas y complejas para proteger tus cuentas.",
                fuente: "https://nordpass.com"
            },
            {
                titulo: "¿Qué es Mattermost?",
                contenido: "Mattermost es una solución de código abierto para la comunicación en equipo, con funciones de recuperación de información integradas.",
                fuente: "https://mattermost.com"
            }
        ];

        function buscar() {
            const query = document.getElementById("searchInput").value.toLowerCase();
            const resultsContainer = document.getElementById("results");
            resultsContainer.innerHTML = ""; // Limpiar resultados anteriores

            if (query.trim() === "") {
                resultsContainer.innerHTML = "<p>Por favor, escribe algo en el campo de búsqueda.</p>";
                return;
            }

            const resultadosFiltrados = database.filter(item => 
                item.titulo.toLowerCase().includes(query) || item.contenido.toLowerCase().includes(query)
            );

            if (resultadosFiltrados.length > 0) {
                resultadosFiltrados.forEach(item => {
                    const resultItem = document.createElement("div");
                    resultItem.classList.add("result-item");
                    resultItem.innerHTML = `
                        <h3>${item.titulo}</h3>
                        <p>${item.contenido}</p>
                        <p class="source"><strong>Fuente:</strong> <a href="${item.fuente}" target="_blank">${item.fuente}</a></p>
                    `;
                    resultsContainer.appendChild(resultItem);
                });
            } else {
                resultsContainer.innerHTML = "<p>No se encontraron resultados para tu búsqueda.</p>";
            }
        }
    </script>
</body>
</html>
