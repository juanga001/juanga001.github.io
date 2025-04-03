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
            line-height: 1.5;
        }
        header {
            background: #2c3e50;
            padding: 15px 0;
            border-bottom: 1px solid #ddd;
            margin-bottom: 20px;
        }
        .header-container {
            display: flex;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        .logo {
            color: white;
            font-size: 1.8em;
            margin-right: 20px;
            font-weight: bold;
            text-decoration: none;
        }
        .logo span {
            color: #3498db;
        }
        .search-box {
            flex-grow: 1;
            max-width: 650px;
            display: flex;
            align-items: stretch;
        }
        .search-input {
            flex-grow: 1;
            padding: 12px 15px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 24px 0 0 24px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            outline: none;
        }
        .search-input:focus {
            border-color: #3498db;
            box-shadow: 0 1px 5px rgba(52, 152, 219, 0.3);
        }
        .search-button {
            background: #3498db;
            color: white;
            border: none;
            padding: 0 25px;
            border-radius: 0 24px 24px 0;
            cursor: pointer;
            font-size: 16px;
            font-weight: 500;
        }
        .search-button:hover {
            background: #2980b9;
        }
        
        /* Contenido principal */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        .search-info {
            margin-bottom: 15px;
            color: #555;
            font-size: 14px;
        }
        .search-stats {
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1px solid #eee;
        }
        
        /* Estilo de resultados al estilo Google */
        .search-results {
            margin-bottom: 30px;
        }
        .search-result {
            margin-bottom: 25px;
            max-width: 650px;
        }
        .result-url {
            color: #006621;
            font-size: 14px;
            margin-bottom: 3px;
        }
        .result-title {
            margin: 0 0 5px;
            font-size: 18px;
        }
        .result-title a {
            color: #1a0dab;
            text-decoration: none;
        }
        .result-title a:hover {
            text-decoration: underline;
        }
        .result-snippet {
            color: #545454;
            font-size: 14px;
            line-height: 1.5;
        }
        
        /* Etiquetas de fact-check */
        .fact-check-badge {
            display: inline-block;
            padding: 2px 8px;
            font-size: 12px;
            font-weight: bold;
            border-radius: 3px;
            margin-right: 10px;
        }
        .verified {
            background-color: #e8f5e9;
            color: #2e7d32;
            border: 1px solid #a5d6a7;
        }
        .false {
            background-color: #ffebee;
            color: #c62828;
            border: 1px solid #ef9a9a;
        }
        .neutral {
            background-color: #fff8e1;
            color: #f57f17;
            border: 1px solid #ffe082;
        }
        
        /* Filtros laterales */
        .search-filters {
            float: left;
            width: 250px;
            margin-right: 30px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            padding: 15px;
        }
        .filter-section {
            margin-bottom: 15px;
        }
        .filter-section h3 {
            margin: 0 0 10px;
            font-size: 16px;
            color: #333;
        }
        .filter-option {
            margin-bottom: 8px;
        }
        .filter-option label {
            display: flex;
            align-items: center;
            font-size: 14px;
            color: #555;
            cursor: pointer;
        }
        .filter-option input {
            margin-right: 8px;
        }
        
        /* Resultados destacados (featured snippet) */
        .featured-snippet {
            background-color: #f5f5f5;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 25px;
            max-width: 650px;
        }
        .featured-snippet h3 {
            margin: 0 0 10px;
            color: #333;
            font-size: 16px;
        }
        .featured-snippet-content {
            font-size: 14px;
            color: #333;
            margin-bottom: 10px;
        }
        .featured-snippet-source {
            font-size: 13px;
            color: #006621;
        }
        
        /* Indicador de carga */
        .loading {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 40px 0;
        }
        .spinner {
            border: 4px solid rgba(0, 0, 0, 0.1);
            width: 36px;
            height: 36px;
            border-radius: 50%;
            border-left-color: #3498db;
            animation: spin 1s linear infinite;
            margin-bottom: 15px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Paginación */
        .pagination {
            max-width: 650px;
            display: flex;
            justify-content: center;
            margin: 30px 0;
        }
        .pagination-item {
            margin: 0 5px;
            padding: 8px 15px;
            border-radius: 4px;
            color: #3498db;
            text-decoration: none;
            font-size: 14px;
        }
        .pagination-item:hover {
            background-color: #e8f4fc;
        }
        .pagination-item.active {
            background-color: #3498db;
            color: white;
        }
        
        /* Footer */
        footer {
            background: #f5f5f5;
            border-top: 1px solid #ddd;
            padding: 20px 0;
            margin-top: 30px;
            color: #555;
            font-size: 13px;
        }
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
        }
        .footer-links a {
            color: #555;
            margin-right: 15px;
            text-decoration: none;
        }
        .footer-links a:hover {
            text-decoration: underline;
        }
        
        /* Adaptación móvil */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                padding: 10px;
            }
            .logo {
                margin-bottom: 15px;
                margin-right: 0;
            }
            .search-box {
                width: 100%;
                max-width: 100%;
            }
            .search-filters {
                float: none;
                width: auto;
                margin-right: 0;
                margin-bottom: 20px;
            }
            .footer-content {
                flex-direction: column;
                text-align: center;
            }
            .footer-links {
                margin-top: 10px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="header-container">
            <a href="#" class="logo">Todo<span>Verdad</span></a>
            <div class="search-box">
                <input type="text" class="search-input" id="searchInput" placeholder="Buscar información verificada...">
                <button class="search-button" onclick="buscar()">Buscar</button>
            </div>
        </div>
    </header>

    <div class="container">
        <div id="results">
            <!-- Resultados de búsqueda aparecerán aquí -->
            <div class="search-stats" id="searchStats" style="display:none;">
                <span id="resultCount">0</span> resultados encontrados (<span id="searchTime">0.0</span> segundos)
            </div>
            
            <div class="welcome-message" id="welcomeMessage">
                <h2>Bienvenido a TodoVerdad</h2>
                <p>Tu buscador de información verificada. Escribe tu consulta y obtendrás resultados verificados contra fuentes confiables.</p>
                <p>Si buscas una noticia falsa, te la desmentiremos con información precisa y verificada.</p>
                
                <h3>Búsquedas populares:</h3>
                <div id="popularSearches" style="margin-top: 15px;">
                    <span class="fact-check-badge verified" onclick="buscarPopular('cambio climático')">Cambio climático</span>
                    <span class="fact-check-badge false" onclick="buscarPopular('vacunas causan autismo')">Vacunas y autismo</span>
                    <span class="fact-check-badge neutral" onclick="buscarPopular('inteligencia artificial')">Inteligencia artificial</span>
                    <span class="fact-check-badge false" onclick="buscarPopular('tierra plana')">Tierra plana</span>
                    <span class="fact-check-badge verified" onclick="buscarPopular('alimentos transgénicos')">Alimentos transgénicos</span>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="footer-content">
            <div class="copyright">© 2025 TodoVerdad - Información verificada y confiable</div>
            <div class="footer-links">
                <a href="#">Sobre nosotros</a>
                <a href="#">Políticas de privacidad</a>
                <a href="#">Contacto</a>
            </div>
        </div>
    </footer>

    <script>
        // Base de datos de verificación de hechos (simulada)
        const factDatabase = {
            "cambio climático": {
                esVerdad: true,
                resultados: [
                    {
                        title: "El cambio climático es real y está respaldado por evidencia científica",
                        url: "https://climate.nasa.gov/evidencia/",
                        displayUrl: "climate.nasa.gov › evidencia",
                        snippet: "Múltiples líneas de evidencia independientes confirman que el planeta se está calentando principalmente debido a actividades humanas como la quema de combustibles fósiles, la deforestación y la agricultura industrial.",
                        factCheck: "VERIFICADO",
                        featuredSnippet: {
                            title: "¿Qué es el cambio climático?",
                            content: "El cambio climático se refiere a cambios a largo plazo en las temperaturas y los patrones climáticos. Desde 1880, la temperatura media global ha aumentado unos 1.1°C, principalmente debido a la quema de combustibles fósiles que genera gases de efecto invernadero.",
                            source: "IPCC - Panel Intergubernamental del Cambio Climático"
                        }
                    },
                    {
                        title: "Efectos del cambio climático en los océanos y ecosistemas marinos",
                        url: "https://www.noaa.gov/education/resource-collections/ocean-coasts/ocean-warming",
                        displayUrl: "noaa.gov › education › ocean-warming",
                        snippet: "El cambio climático provoca el aumento del nivel del mar, la acidificación de los océanos y cambios en los patrones de corrientes marinas, lo que afecta a ecosistemas marinos en todo el mundo.",
                        factCheck: "VERIFICADO"
                    },
                    {
                        title: "Impactos actuales y proyectados del cambio climático - ONU",
                        url: "https://www.un.org/es/climatechange/science/causes-effects-climate-change",
                        displayUrl: "un.org › climatechange › causes-effects",
                        snippet: "Los efectos del cambio climático ya son visibles: aumento de eventos climáticos extremos, pérdida de biodiversidad, escasez de agua y amenazas a la seguridad alimentaria. Sin acción, los riesgos aumentarán significativamente.",
                        factCheck: "VERIFICADO"
                    }
                ]
            },
            "vacunas causan autismo": {
                esVerdad: false,
                resultados: [
                    {
                        title: "Las vacunas NO causan autismo: Desmintiendo un mito peligroso",
                        url: "https://www.cdc.gov/vaccinesafety/concerns/autism.html",
                        displayUrl: "cdc.gov › vaccinesafety › concerns › autism",
                        snippet: "Numerosos estudios científicos rigurosos y a gran escala han demostrado que no existe ninguna relación entre las vacunas y el autismo. El estudio original que sugirió esta relación fue retractado por ser fraudulento.",
                        factCheck: "DESMENTIDO",
                        featuredSnippet: {
                            title: "¿Causan las vacunas autismo?",
                            content: "FALSO: Estudios que involucran a más de un millón de niños han demostrado que no existe relación entre las vacunas y el autismo. El estudio de 1998 que originalmente sugirió esta conexión fue retractado por la revista médica The Lancet debido a graves fallas metodológicas y conflictos de interés no declarados.",
                            source: "Organización Mundial de la Salud (OMS)"
                        }
                    },
                    {
                        title: "La historia completa del fraude de las vacunas y el autismo",
                        url: "https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3136032/",
                        displayUrl: "ncbi.nlm.nih.gov › pmc › articles › PMC3136032",
                        snippet: "Cómo un artículo fraudulento publicado en The Lancet por Andrew Wakefield desencadenó un movimiento antivacunas basado en información falsa, causando brotes de enfermedades prevenibles.",
                        factCheck: "DESMENTIDO"
                    },
                    {
                        title: "Consenso científico: Las vacunas son seguras y no causan autismo",
                        url: "https://www.who.int/es/news-room/questions-and-answers/item/vaccines-and-immunization-myths-and-misconceptions",
                        displayUrl: "who.int › news-room › questions-and-answers",
                        snippet: "La OMS confirma la seguridad de las vacunas y desmiente la relación con el autismo. Las vacunas previenen entre 2 y 3 millones de muertes cada año y son uno de los mayores logros de la salud pública.",
                        factCheck: "DESMENTIDO"
                    }
                ]
            },
            "tierra plana": {
                esVerdad: false,
                resultados: [
                    {
                        title: "La Tierra no es plana: Evidencia irrefutable de la esfericidad terrestre",
                        url: "https://www.nasa.gov/multimedia/imagegallery/image_feature_1249.html",
                        displayUrl: "nasa.gov › multimedia › image_feature_1249",
                        snippet: "FALSO: La Tierra no es plana, sino esférica (técnicamente, un geoide ligeramente achatado en los polos). Esta realidad ha sido confirmada por miles de imágenes satelitales, vuelos transoceánicos, mediciones geodésicas y observaciones astronómicas desde hace siglos.",
                        factCheck: "DESMENTIDO",
                        featuredSnippet: {
                            title: "¿Es plana la Tierra?",
                            content: "FALSO: La forma esférica de la Tierra es un hecho científico comprobado por múltiples evidencias: fotografías desde el espacio, comportamiento de la sombra terrestre durante eclipses lunares, observación de barcos desapareciendo en el horizonte, gravitación, y miles de vuelos diarios alrededor del mundo que siguen rutas consistentes con una Tierra esférica.",
                            source: "NASA - Administración Nacional de Aeronáutica y el Espacio"
                        }
                    },
                    {
                        title: "Comprobaciones históricas de la esfericidad de la Tierra",
                        url: "https://www.nationalgeographic.org/encyclopedia/eratosthenes-ancient-geographer/",
                        displayUrl: "nationalgeographic.org › encyclopedia › eratosthenes",
                        snippet: "Desde la antigüedad, científicos como Eratóstenes (276-194 a.C.) calcularon correctamente la circunferencia de la Tierra utilizando observaciones de sombras. Los navegantes de todas las civilizaciones avanzadas han usado la curvatura terrestre para calcular sus rutas.",
                        factCheck: "VERIFICADO"
                    },
                    {
                        title: "Por qué persiste el mito de la Tierra plana a pesar de la evidencia",
                        url: "https://www.scientificamerican.com/article/flat-earth-psychology-why-people-believe/",
                        displayUrl: "scientificamerican.com › article › flat-earth-psychology",
                        snippet: "Análisis psicológico y sociológico del movimiento terraplanista contemporáneo. Las teorías conspirativas ofrecen explicaciones simples a realidades complejas y crean comunidades de pertenencia, a pesar de contradecir la evidencia científica fundamental.",
                        factCheck: "ANÁLISIS"
                    }
                ]
            },
            "alimentos transgénicos": {
                esVerdad: true,
                resultados: [
                    {
                        title: "La seguridad de los alimentos genéticamente modificados (transgénicos)",
                        url: "https://www.who.int/news-room/questions-and-answers/item/food-genetically-modified",
                        displayUrl: "who.int › news-room › questions-and-answers › food-gm",
                        snippet: "Según el consenso científico actual, los alimentos transgénicos disponibles en el mercado son generalmente seguros para el consumo humano. Múltiples estudios realizados por organizaciones como la OMS, la FAO y diversas academias nacionales de ciencias respaldan esta conclusión.",
                        factCheck: "VERIFICADO",
                        featuredSnippet: {
                            title: "¿Son seguros los alimentos transgénicos?",
                            content: "VERIFICADO: La comunidad científica considera que los alimentos transgénicos aprobados para el consumo son tan seguros como sus contrapartes convencionales. Cada nuevo producto transgénico se somete a evaluaciones de seguridad específicas antes de su aprobación. No existe evidencia científica de que los alimentos transgénicos comercializados tengan efectos negativos para la salud humana.",
                            source: "Organización de las Naciones Unidas para la Alimentación y la Agricultura (FAO)"
                        }
                    },
                    {
                        title: "Beneficios y desafíos de los cultivos transgénicos en la agricultura actual",
                        url: "https://www.fao.org/agricultural-biotechnologies/es/",
                        displayUrl: "fao.org › agricultural-biotechnologies",
                        snippet: "Análisis de cómo los cultivos genéticamente modificados pueden contribuir a la seguridad alimentaria, al aumentar rendimientos y reducir el uso de pesticidas, mientras se consideran preocupaciones ambientales y socioeconómicas.",
                        factCheck: "VERIFICADO"
                    },
                    {
                        title: "Evaluación de riesgos y regulación de los alimentos transgénicos",
                        url: "https://www.efsa.europa.eu/es/topics/topic/gmo",
                        displayUrl: "efsa.europa.eu › topics › topic › gmo",
                        snippet: "La Autoridad Europea de Seguridad Alimentaria explica los rigurosos procesos de evaluación que siguen los alimentos transgénicos antes de ser aprobados para el consumo en la UE, incluyendo estudios toxicológicos, alergénicos y ambientales.",
                        factCheck: "INFORMATIVO"
                    }
                ]
            },
            "inteligencia artificial": {
                esVerdad: null,
                resultados: [
                    {
                        title: "¿Qué es la inteligencia artificial? Conceptos básicos y aplicaciones",
                        url: "https://www.ibm.com/es-es/topics/artificial-intelligence",
                        displayUrl: "ibm.com › es-es › topics › artificial-intelligence",
                        snippet: "La inteligencia artificial (IA) combina ciencia de datos, algoritmos y computación para permitir el razonamiento y aprendizaje automático en máquinas. Actualmente se aplica en medicina, finanzas, transporte, educación y otras áreas.",
                        factCheck: "INFORMATIVO",
                        featuredSnippet: {
                            title: "Inteligencia Artificial: Definición y alcance",
                            content: "La inteligencia artificial se refiere a sistemas informáticos diseñados para realizar tareas que tradicionalmente requerían inteligencia humana. Estos sistemas utilizan técnicas como el aprendizaje automático, el procesamiento del lenguaje natural y la visión artificial para analizar datos, reconocer patrones, tomar decisiones y resolver problemas de manera autónoma.",
                            source: "Universidad de Stanford - Instituto de IA Centrada en el Humano"
                        }
                    },
                    {
                        title: "Beneficios y riesgos de la inteligencia artificial en la sociedad actual",
                        url: "https://www.weforum.org/agenda/2021/01/benefits-risks-artificial-intelligence-society/",
                        displayUrl: "weforum.org › agenda › benefits-risks-ai-society",
                        snippet: "La IA ofrece beneficios en productividad, medicina personalizada y resolución de problemas complejos, pero también presenta desafíos como sesgos algorítmicos, privacidad, desplazamiento laboral y preocupaciones éticas que requieren gobernanza adecuada.",
                        factCheck: "ANÁLISIS"
                    },
                    {
                        title: "Mitos comunes sobre la inteligencia artificial: separando realidad de ficción",
                        url: "https://www.oecd.org/going-digital/ai/myths-and-realities-of-ai.pdf",
                        displayUrl: "oecd.org › going-digital › ai › myths-and-realities",
                        snippet: "Análisis de conceptos erróneos populares sobre la IA, incluyendo temores infundados sobre una 'superinteligencia' hostil a corto plazo, así como expectativas irrealistas sobre capacidades actuales, para establecer un debate público más informado.",
                        factCheck: "VERIFICACIÓN MIXTA"
                    }
                ]
            }
        };

        // Función de búsqueda
        function buscar() {
            const query = document.getElementById("searchInput").value.trim().toLowerCase();
            const resultsContainer = document.getElementById("results");
            
            if (query === "") {
                // Si no hay consulta, mantener mensaje de bienvenida
                return;
            }
            
            // Ocultar mensaje de bienvenida
            document.getElementById("welcomeMessage").style.display = "none";
            
            // Mostrar indicador de carga
            resultsContainer.innerHTML = `
                <div class="loading">
                    <div class="spinner"></div>
                    <p>Buscando resultados verificados para "${query}"...</p>
                </div>
            `;
            
            // Simulamos tiempo de búsqueda (entre 0.5 y 1.5 segundos)
            const searchTime = Math.random() * (1.5 - 0.5) + 0.5;
            
            setTimeout(() => {
                // Intentar encontrar resultados exactos en nuestra base de datos
                let resultados = null;
                let esVerdad = null;
                
                // Buscar coincidencias exactas o parciales
                for (const key in factDatabase) {
                    if (query === key) {
                        resultados = factDatabase[key].resultados;
                        esVerdad = factDatabase[key].esVerdad;
                        break;
                    }
                }
                
                // Si no hay coincidencia exacta, buscar palabras clave
                if (!resultados) {
                    const palabrasClave = query.split(" ");
                    
                    for (const key in factDatabase) {
                        for (const palabra of palabrasClave) {
                            if (palabra.length > 3 && key.includes(palabra)) {
                                resultados = factDatabase[key].resultados;
                                esVerdad = factDatabase[key].esVerdad;
                                break;
                            }
                        }
                        if (resultados) break;
                    }
                }
                
                // Si aún no hay resultados, generar resultados genéricos
                if (!resultados) {
                    resultados = [
                        {
                            title: `Resultados para "${query}"`,
                            url: "https://ejemplo.com/resultados",
                            displayUrl: "ejemplo.com › resultados",
                            snippet: `En un sistema real, aquí se mostrarían resultados de una búsqueda real para "${query}" a través de APIs como Google Search, Bing o tu propio índice de contenidos verificados.`,
                            factCheck: "SIN VERIFICACIÓN"
                        },
                        {
                            title: `Información sobre "${query}" - Fuentes confiables`,
                            url: "https://fuentes-confiables.com/info",
                            displayUrl: "fuentes-confiables.com › info",
                            snippet: `Una implementación completa mostraría aquí resultados de sitios verificados y confiables relacionados con tu búsqueda de "${query}".`,
                            factCheck: "SIN VERIFICACIÓN"
                        },
                        {
                            title: `Análisis recientes sobre "${query}"`,
                            url: "https://analisis-verificados.org/tendencias",
                            displayUrl: "analisis-verificados.org › tendencias",
                            snippet: `En este lugar aparecerían análisis recientes, estudios académicos y reportes verificados relacionados con tu consulta.`,
                            factCheck: "SIN VERIFICACIÓN"
                        }
                    ];
                }
                
                // Construir los resultados
                let resultsHTML = `
                    <div class="search-stats" id="searchStats" style="display:block;">
                        <span id="resultCount">${resultados.length}</span> resultados encontrados (<span id="searchTime">${searchTime.toFixed(2)}</span> segundos)
                    </div>
                `;
                
                // Destacado (Featured Snippet) si existe
                const featuredResult = resultados.find(r => r.featuredSnippet);
                if (featuredResult) {
                    resultsHTML += `
                        <div class="featured-snippet">
                            <h3>${featuredResult.featuredSnippet.title}</h3>
                            <div class="featured-snippet-content">${featuredResult.featuredSnippet.content}</div>
                            <div class="featured-snippet-source">Fuente: ${featuredResult.featuredSnippet.source}</div>
                        </div>
                    `;
                }
                
                // Construir cada resultado
                resultsHTML += '<div class="search-results">';
                resultados.forEach(result => {
                    let factCheckClass = "neutral";
                    if (result.factCheck === "VERIFICADO") factCheckClass = "verified";
                    if (result.factCheck === "DESMENTIDO") factCheckClass = "false";
                    
                    resultsHTML += `
                        <div class="search-result">
                            <div class="result-url">${result.displayUrl}</div>
                            <h3 class="result-title"><a href="${result.url}" target="_blank">${result.title}</a> 
                                <span class="fact-check-badge ${factCheckClass}">${result.factCheck}</span>
                            </h3>
                            <div class="result-snippet">${result.snippet}</div>
                        </div>
                    `;
                });
                resultsHTML += '</div>';
                
                // Paginación (simulada)
                resultsHTML += `
                    <div class="pagination">
                        <a href="#" class="pagination-item active">1</a>
                        <a href="#" class="pagination-item">2</a>
                        <a href="#" class="pagination-item">3</a>
                        <a href="#" class="pagination-item">4</a>
                        <a href="#" class="pagination-item">5</a>
                        <a href="#" class="pagination-item">Siguiente</a>
                    </div>
                `;
                
                // Mostrar resultados
                resultsContainer.innerHTML = resultsHTML
