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
        .fact-true {
            border-left: 5px solid #27ae60;
        }
        .fact-false {
            border-left: 5px solid #e74c3c;
        }
        .fact-status {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 3px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        .status-true {
            background: #27ae60;
            color: white;
        }
        .status-false {
            background: #e74c3c;
            color: white;
        }
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px 0;
            margin-top: 30px;
        }
        footer a {
            color: #3498db;
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
        <p>Contacto: <a href="mailto:info@todoquesabes.com">info@todoquesabes.com</a></p>
        <p>© 2025 Todo Lo Que Quieras Saber</p>
    </footer>

    <script>
        // Base de datos con información verificada y desmentidos
        const database = [
            // Información verificada
            {
                titulo: "¿Es cierto que el cambio climático afecta a los océanos?",
                contenido: "Sí, el cambio climático provoca el aumento del nivel del mar, la acidificación de los océanos y cambios en los patrones de corrientes marinas.",
                fuente: "https://www.ipcc.ch",
                esVerdad: true
            },
            {
                titulo: "¿El agua hierve a 100°C en cualquier lugar?",
                contenido: "No, el punto de ebullición del agua depende de la presión atmosférica. A mayor altitud, el agua hierve a temperaturas más bajas.",
                fuente: "https://www.science.org",
                esVerdad: true
            },
            {
                titulo: "¿Es seguro usar contraseñas comunes?",
                contenido: "No, las contraseñas comunes son fáciles de adivinar. Usa contraseñas únicas y complejas para proteger tus cuentas.",
                fuente: "https://nordpass.com",
                esVerdad: true
            },
            {
                titulo: "¿Qué es Mattermost?",
                contenido: "Mattermost es una solución de código abierto para la comunicación en equipo, con funciones de recuperación de información integradas.",
                fuente: "https://mattermost.com",
                esVerdad: true
            },
            
            // Noticias falsas con desmentidos
            {
                titulo: "¿La vacuna contra el COVID-19 contiene microchips?",
                contenido: "FALSO: Esta afirmación es completamente falsa. Las vacunas contra el COVID-19 no contienen microchips ni dispositivos de rastreo. Las vacunas contienen ingredientes médicos como antígenos, conservantes, estabilizadores y diluyentes, todos ellos listados públicamente por las autoridades sanitarias.",
                fuente: "https://www.who.int/es/emergencies/diseases/novel-coronavirus-2019/covid-19-vaccines/advice",
                esVerdad: false,
                noticiaFalsa: "Las vacunas contra el COVID-19 contienen microchips para rastrear a la población"
            },
            {
                titulo: "¿El 5G causa COVID-19?",
                contenido: "FALSO: No existe ninguna relación entre la tecnología 5G y el COVID-19. El COVID-19 es causado por el virus SARS-CoV-2, que se propaga principalmente a través de gotículas respiratorias. Las redes 5G utilizan ondas de radio no ionizantes que no pueden transmitir virus ni causar enfermedades infecciosas.",
                fuente: "https://www.who.int/es/news-room/q-a-detail/radiation-5g-mobile-networks-and-health",
                esVerdad: false,
                noticiaFalsa: "Las redes 5G causan o propagan el coronavirus"
            },
            {
                titulo: "¿Beber lejía o desinfectante cura el COVID-19?",
                contenido: "FALSO Y PELIGROSO: Consumir lejía, desinfectante o cualquier producto de limpieza es extremadamente peligroso y puede causar graves daños a la salud, incluyendo la muerte. Estos productos son tóxicos y no tienen ningún efecto curativo contra el COVID-19 u otras enfermedades.",
                fuente: "https://www.fda.gov/consumers/articulos-en-espanol/peligro-no-beba-ni-se-inyecte-blanqueador-u-otros-desinfectantes",
                esVerdad: false,
                noticiaFalsa: "Beber desinfectante o lejía puede curar el coronavirus"
            },
            {
                titulo: "¿La Tierra es plana?",
                contenido: "FALSO: La Tierra no es plana, sino esférica (técnicamente, un geoide ligeramente achatado en los polos). Esta realidad ha sido confirmada por miles de imágenes satelitales, vuelos transoceánicos, mediciones geodésicas y observaciones astronómicas desde hace siglos.",
                fuente: "https://www.nasa.gov/multimedia/imagegallery/image_feature_1249.html",
                esVerdad: false,
                noticiaFalsa: "La Tierra es plana y las agencias espaciales mienten"
            },
            {
                titulo: "¿El cambio climático es un engaño?",
                contenido: "FALSO: El cambio climático es real y está respaldado por un consenso científico abrumador. Múltiples líneas de evidencia independientes confirman que el planeta se está calentando principalmente debido a actividades humanas como la quema de combustibles fósiles, la deforestación y la agricultura industrial.",
                fuente: "https://climate.nasa.gov/evidencia/",
                esVerdad: false,
                noticiaFalsa: "El cambio climático es un engaño inventado por científicos y políticos"
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

            // Buscar tanto en información verdadera como en noticias falsas
            const resultadosFiltrados = database.filter(item => 
                item.titulo.toLowerCase().includes(query) || 
                item.contenido.toLowerCase().includes(query) || 
                (item.noticiaFalsa && item.noticiaFalsa.toLowerCase().includes(query))
            );

            if (resultadosFiltrados.length > 0) {
                resultadosFiltrados.forEach(item => {
                    const resultItem = document.createElement("div");
                    resultItem.classList.add("result-item");
                    
                    // Añadir clase según si es verdad o falso
                    resultItem.classList.add(item.esVerdad ? "fact-true" : "fact-false");
                    
                    // Construir el contenido
                    let contenido = `
                        <h3>${item.titulo}</h3>
                        <div class="fact-status ${item.esVerdad ? 'status-true' : 'status-false'}">
                            ${item.esVerdad ? 'VERIFICADO' : 'DESMENTIDO'}
                        </div>
                    `;
                    
                    // Si es una noticia falsa, mostrar primero cuál es
                    if (!item.esVerdad && item.noticiaFalsa) {
                        contenido += `<p><strong>Noticia falsa:</strong> "${item.noticiaFalsa}"</p>`;
                    }
                    
                    contenido += `
                        <p>${item.contenido}</p>
                        <p class="source"><strong>Fuente:</strong> <a href="${item.fuente}" target="_blank">${item.fuente}</a></p>
                    `;
                    
                    resultItem.innerHTML = contenido;
                    resultsContainer.appendChild(resultItem);
                });
            } else {
                resultsContainer.innerHTML = `
                    <div class="result-item">
                        <h3>No se encontraron resultados</h3>
                        <p>No tenemos información sobre "${query}" en nuestra base de datos.</p>
                        <p>Intenta con otra búsqueda o contáctanos si crees que deberíamos añadir esta información.</p>
                    </div>
                `;
            }
        }

        // Permitir búsqueda al presionar Enter
        document.getElementById("searchInput").addEventListener("keyup", function(event) {
            if (event.key === "Enter") {
                buscar();
            }
        });
    </script>
</body>
</html>
