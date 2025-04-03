<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Derecho y CS - Uruguay 2025</title>
    <style>
        /* Estilos básicos */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #f5f5f5;
            color: #333;
        }
        header {
            background: #2c3e50;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        nav {
            background: #34495e;
            padding: 10px 0;
        }
        nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            justify-content: center;
        }
        nav li {
            margin: 0 15px;
        }
        nav a {
            color: white;
            text-decoration: none;
        }
        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 20px;
        }
        .materias-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        .materia-card {
            background: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            text-align: center;
            transition: transform 0.3s ease;
        }
        .materia-card:hover {
            transform: scale(1.05);
        }
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px 0;
            margin-top: 30px;
        }
        @media (max-width: 600px) {
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            nav li {
                margin: 5px 0;
            }
        }

        /* Estilos para las unidades */
        .unidad {
            margin-top: 40px;
        }
        .unidad h3 {
            color: #2c3e50;
            margin-bottom: 10px;
        }
        .tema {
            margin-bottom: 20px;
        }
        .tema h4 {
            color: #34495e;
            margin-bottom: 5px;
        }
        .tema p {
            line-height: 1.6;
        }
        .fuente {
            font-size: 0.9em;
            color: #777;
        }
    </style>
</head>
<body>
    <header>
        <h1>Bachillerato Derecho y Ciencias Sociales</h1>
        <p>Recursos educativos 2025 - Uruguay</p>
    </header>

    <nav>
        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#materias">Materias</a></li>
            <li><a href="mailto:juangabrielsilvera00@gmail.com">Contacto</a></li>
        </ul>
    </nav>

    <div class="container">
        <!-- Sección de Materias -->
        <h2 id="materias">Materias (6° año)</h2>
        <div class="materias-grid">
            <a href="#derecho" class="materia-card">
                <h3>Derecho y Ciencia Política</h3>
                <p>6° año</p>
            </a>
            <a href="#filosofia" class="materia-card">
                <h3>Filosofía y Crítica</h3>
                <p>6° año</p>
            </a>
            <a href="#metodologia" class="materia-card">
                <h3>Metodología de Investigación</h3>
                <p>6° año</p>
            </a>
        </div>

        <!-- Contenido detallado de las materias -->
        <div id="derecho" class="unidad">
            <h2>Derecho y Ciencia Política</h2>
            <div class="tema">
                <h4>Unidad 1: Introducción al Derecho</h4>
                <p>En esta unidad, se estudian los conceptos fundamentales del derecho, su evolución histórica y su relación con la sociedad.</p>
                <p><strong>Temas:</strong> Concepto de derecho, fuentes del derecho, principios generales.</p>
                <p class="fuente"><strong>Fuente:</strong> <a href="https://www.ejemplo.com/derecho" target="_blank">https://www.ejemplo.com/derecho</a></p>
            </div>
            <div class="tema">
                <h4>Unidad 2: Sistema Político Uruguayo</h4>
                <p>Se analiza la estructura del sistema político uruguayo, incluyendo el Poder Ejecutivo, Legislativo y Judicial.</p>
                <p><strong>Temas:</strong> Constitución Nacional, división de poderes, partidos políticos.</p>
                <p class="fuente"><strong>Fuente:</strong> <a href="https://www.ejemplo.com/politica" target="_blank">https://www.ejemplo.com/politica</a></p>
            </div>
        </div>

        <div id="filosofia" class="unidad">
            <h2>Filosofía y Crítica</h2>
            <div class="tema">
                <h4>Unidad 1: Introducción a la Filosofía</h4>
                <p>Esta unidad explora los orígenes de la filosofía, sus principales corrientes y su importancia en la reflexión crítica.</p>
                <p><strong>Temas:</strong> Filosofía antigua, ética, lógica.</p>
                <p class="fuente"><strong>Fuente:</strong> <a href="https://www.ejemplo.com/filosofia" target="_blank">https://www.ejemplo.com/filosofia</a></p>
            </div>
            <div class="tema">
                <h4>Unidad 2: Pensamiento Crítico</h4>
                <p>Se enfatiza en el desarrollo de habilidades para el análisis crítico de ideas y argumentos.</p>
                <p><strong>Temas:</strong> Falacias lógicas, razonamiento deductivo e inductivo.</p>
                <p class="fuente"><strong>Fuente:</strong> <a href="https://www.ejemplo.com/critica" target="_blank">https://www.ejemplo.com/critica</a></p>
            </div>
        </div>

        <div id="metodologia" class="unidad">
            <h2>Metodología de Investigación</h2>
            <div class="tema">
                <h4>Unidad 1: Fundamentos de la Investigación</h4>
                <p>Introducción a los métodos y técnicas utilizados en la investigación científica y social.</p>
                <p><strong>Temas:</strong> Tipos de investigación, diseño metodológico, recolección de datos.</p>
                <p class="fuente"><strong>Fuente:</strong> <a href="https://www.ejemplo.com/metodologia" target="_blank">https://www.ejemplo.com/metodologia</a></p>
            </div>
            <div class="tema">
                <h4>Unidad 2: Análisis de Datos</h4>
                <p>Se enseñan herramientas para el análisis cuantitativo y cualitativo de datos.</p>
                <p><strong>Temas:</strong> Herramientas estadísticas, interpretación de resultados.</p>
                <p class="fuente"><strong>Fuente:</strong> <a href="https://www.ejemplo.com/analisis" target="_blank">https://www.ejemplo.com/analisis</a></p>
            </div>
        </div>
    </div>

    <footer>
        <p>Contacto: <a href="mailto:juangabrielsilvera00@gmail.com" style="color: #3498db;">juangabrielsilvera00@gmail.com</a></p>
        <p>© 2025 Recursos Educativos - Uruguay</p>
    </footer>
</body>
</html>
