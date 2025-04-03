<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Historia - 6° Derecho Uruguay</title>
    <link rel="stylesheet" href="../css/style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <header>
        <div class="container">
            <h1>Historia - 6° Derecho</h1>
            <p>Programa 2025 - Recursos educativos</p>
            
            <div class="search-bar">
                <form action="../search.html" method="get">
                    <input type="text" name="q" placeholder="Buscar en Historia...">
                    <button type="submit"><i class="fas fa-search"></i></button>
                </form>
            </div>
        </div>
    </header>

    <nav>
        <div class="container">
            <ul>
                <li><a href="../index.html">Inicio</a></li>
                <li><a href="#unidades">Unidades</a></li>
                <li><a href="#recursos">Recursos</a></li>
                <li><a href="../contact.html">Contacto</a></li>
            </ul>
        </div>
    </nav>

    <main class="container">
        <section id="introduccion">
            <h2>Introducción a la Historia para Derecho</h2>
            <p>El estudio de la historia en el contexto de la formación jurídica permite comprender los procesos sociales, políticos y económicos que han dado forma a las instituciones y normas que rigen nuestra sociedad.</p>
            <img src="../images/historia-derecho.jpg" alt="Historia y Derecho" style="max-width: 100%; height: auto; margin: 1rem 0;">
            <p>Este espacio recopila recursos para las unidades del programa 2025, con énfasis en aquellos aspectos históricos relevantes para la comprensión del desarrollo del derecho en Uruguay y el mundo.</p>
        </section>

        <section id="unidades">
            <h2>Unidades del Curso</h2>
            
            <div class="unidad">
                <h3 id="unidad1">Unidad 1: Fundamentos Históricos del Derecho</h3>
                <div class="temas">
                    <h4>Temas:</h4>
                    <ul>
                        <li><a href="#derecho-romano">Derecho Romano y su influencia</a></li>
                        <li><a href="#revoluciones">Revoluciones burguesas y su impacto jurídico</a></li>
                        <li><a href="#codigos">Formación de los códigos modernos</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="unidad">
                <h3 id="unidad2">Unidad 2: El Batllismo y la Transformación Jurídica en Uruguay</h3>
                <div class="temas">
                    <h4>Temas:</h4>
                    <ul>
                        <li><a href="#batllismo">Contexto histórico del Batllismo</a></li>
                        <li><a href="#reformas">Reformas jurídicas batllistas</a></li>
                        <li><a href="#impacto">Impacto en el derecho laboral y social</a></li>
                    </ul>
                </div>
            </div>
            
            <!-- Más unidades según el programa -->
        </section>

        <section id="batllismo" class="contenido-tema">
            <h2>El Batllismo en Uruguay</h2>
            <img src="../images/batlle-ordonez.jpg" alt="José Batlle y Ordóñez" class="img-tema">
            
            <h3>Introducción</h3>
            <p>El batllismo fue un movimiento político y social liderado por José Batlle y Ordóñez (1856-1929) que transformó Uruguay a principios del siglo XX, sentando las bases del Estado de bienestar uruguayo y realizando profundas reformas jurídicas.</p>
            
            <h3>Contexto Histórico</h3>
            <p>El Uruguay de fines del siglo XIX presentaba una sociedad marcada por...</p>
            
            <h3>Principales Reformas Jurídicas</h3>
            <ul>
                <li>Ley de 8 horas laborales (1915)</li>
                <li>Ley de divorcio por sola voluntad de la mujer (1913)</li>
                <li>Creación de empresas estatales</li>
                <li>Reforma constitucional de 1917</li>
            </ul>
            
            <h3>Recursos Adicionales</h3>
            <div class="recursos">
                <a href="../documents/batllismo-documento.pdf" class="recurso-link" target="_blank">
                    <i class="fas fa-file-pdf"></i> Documento completo sobre el Batllismo
                </a>
                <a href="https://www.archivodeprensa.edu.uy/batllismo" class="recurso-link" target="_blank">
                    <i class="fas fa-external-link-alt"></i> Archivo de prensa batllista
                </a>
            </div>
            
            <div class="fuentes">
                <h4>Fuentes:</h4>
                <ul>
                    <li>Caetano, G. (2011). "La era batllista". Ediciones de la Banda Oriental.</li>
                    <li>Archivo General de la Nación. (2020). "Documentos del batllismo".</li>
                </ul>
            </div>
        </section>
        
        <!-- Más temas según las unidades -->

        <section id="comentarios">
            <h2>Comentarios y Discusión</h2>
            <div class="comentarios-container">
                <form class="comentario-form">
                    <textarea placeholder="Deja tu comentario o pregunta sobre este tema..." required></textarea>
                    <button type="submit">Publicar comentario</button>
                </form>
                
                <div class="comentarios-list">
                    <!-- Los comentarios se cargarían aquí dinámicamente -->
                    <div class="comentario">
                        <p class="comentario-autor">Ana P. - 10/03/2025</p>
                        <p class="comentario-texto">¿Dónde puedo encontrar más información sobre las reformas laborales del batllismo?</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>© 2025 Blog Educativo 6° Derecho Uruguay</p>
            <p>Contacto: <a href="mailto:juangabrielsilvera00@gmail.com">juangabrielsilvera00@gmail.com</a></p>
            <p>Este contenido es educativo y sin fines de lucro. Todas las fuentes están citadas.</p>
        </div>
    </footer>

    <script src="../js/script.js"></script>
</body>
</html>



