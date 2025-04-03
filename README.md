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
            padding: 15px;
            font-size: 1.2em;
            border: 2px solid #34495e;
            border-radius: 5px 0 0 5px;
        }
        .search-container button {
            padding: 15px 20px;
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
        .fact-neutral {
            border-left: 5px solid #f39c12;
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
        .status-neutral {
            background: #f39c12;
            color: white;
        }
        .loading {
            text-align: center;
            padding: 40px;
            font-size: 1.2em;
        }
        .loader {
            border: 5px solid #f3f3f3;
            border-top: 5px solid #3498db;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 20px auto;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
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
        .advanced-options {
            text-align: center;
            margin: 10px 0 20px;
        }
        .trending {
            background: #ecf0f1;
            padding: 15px;
            border-radius: 8px;
            margin: 20px auto;
            max-width: 1200px;
        }
        .trending h3 {
            margin-top: 0;
            color: #2c3e50;
        }
        .trending-items {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .trending-item {
            background: white;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }
        .trending-item:hover {
            background: #e1e8ed;
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

    <div class="advanced-options">
        <label>
            <input type="checkbox" id="factCheckOnly" checked> 
            Verificar información automáticamente
        </label>
    </div>

    <div class="trending">
        <h3>Búsquedas populares y noticias verificadas</h3>
        <div class="trending-items" id="trendingItems">
            <!-- Los temas tendencia se cargarán aquí -->
        </div>
    </div>

    <div class="results" id="results">
        <!-- Los resultados aparecerán aquí -->
    </div>

    <footer>
        <p>Contacto: <a href="mailto:info@todoquesabes.com">info@todoquesabes.com</a></p>
        <p>© 2025 Todo Lo Que Quieras Saber</p>
    </footer>

    <script>
        // Base de datos local con información verificada y desmentidos
        const localDatabase = [
            // Información verificada
            {
                titulo: "¿Es cierto que el cambio climático afecta a los océanos?",
                contenido: "Sí, el cambio climático provoca el aumento del nivel del mar, la acidificación de los océanos y cambios en los patrones de corrientes marinas.",
                fuente: "https://www.ipcc.ch",
                esVerdad: true
