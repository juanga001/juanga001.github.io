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
    </style>
</head>
<body>
    <header>
        <h1>Bachillerato Derecho y Ciencias Sociales</h1>
        <p>Recursos educativos 2025 - Uruguay</p>
    </header>

    <nav>
        <ul>
            <li><a href="index.html">Inicio</a></li>
            <li><a href="#materias">Materias</a></li>
            <li><a href="mailto:juangabrielsilvera00@gmail.com">Contacto</a></li>
        </ul>
    </nav>

    <div class="container">
        <h2 id="materias">Materias</h2>
        <div class="materias-grid">
            <a href="materias/derecho.html" class="materia-card">
                <h3>Derecho y Ciencia Política</h3>
                <p>5° y 6° año</p>
            </a>
            <a href="materias/administracion.html" class="materia-card">
                <h3>Administración y Contabilidad</h3>
                <p>6° año</p>
            </a>
            <a href="materias/filosofia.html" class="materia-card">
                <h3>Filosofía y Crítica</h3>
                <p>5° año</p>
            </a>
            <a href="materias/metodologia.html" class="materia-card">
                <h3>Metodología de Investigación</h3>
                <p>6° año</p>
            </a>
            <a href="materias/economia.html" class="materia-card">
                <h3>Economía y Educación Financiera</h3>
                <p>5° año</p>
            </a>
            <a href="materias/literatura.html" class="materia-card">
                <h3>Literatura</h3>
                <p>5° año</p>
            </a>
            <a href="materias/historia.html" class="materia-card">
                <h3>Historia</h3>
                <p>5° y 6° año</p>
            </a>
            <a href="materias/ingles.html" class="materia-card">
                <h3>Inglés</h3>
                <p>5° año</p>
            </a>
            <a href="materias/matematica.html" class="materia-card">
                <h3>Matemática CSHI</h3>
                <p>5° año</p>
            </a>
        </div>
    </div>

    <footer>
        <p>Contacto: <a href="mailto:juangabrielsilvera00@gmail.com" style="color: #3498db;">juangabrielsilvera00@gmail.com</a></p>
        <p>© 2025 Recursos Educativos - Uruguay</p>
    </footer>
</body>
</html>
