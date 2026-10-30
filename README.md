```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página Personal - Luisa</title>
    <style>
        :root {
            --bg-body: #0a0a0c;
            --bg-card: #1c142e;
            --text-main: #e6dfff;
            --accent-purple: #bb86fc;
            --accent-lila: #dcc8ff;
            --border-card: #3a2a5c;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-body);
            color: var(--text-main);
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        header {
            text-align: center;
            margin: 40px 0;
        }

        header h1 {
            font-size: 2.8rem;
            color: var(--accent-purple);
            text-shadow: 0 0 10px rgba(187, 134, 252, 0.5);
            margin-bottom: 5px;
        }

        header p {
            color: var(--accent-lila);
            font-size: 1.1rem;
            font-weight: 300;
        }

        main {
            width: 100%;
            max-width: 800px;
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .card {
            background-color: var(--bg-card);
            border: 1px solid var(--border-card);
            border-radius: 16px;
            padding: 30px;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease, border-color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-purple);
        }

        .card-content {
            flex: 1;
        }

        .card h2 {
            color: var(--accent-purple);
            margin-bottom: 15px;
            font-size: 1.6rem;
            border-bottom: 2px solid var(--border-card);
            padding-bottom: 5px;
            display: inline-block;
        }

        .card p, .card ul {
            font-size: 1rem;
            line-height: 1.6;
            color: var(--text-main);
        }

        .card ul {
            list-style-type: none;
            margin-left: 5px;
        }

        .card ul li::before {
            content: "✦ ";
            color: var(--accent-purple);
        }

        .chibi-container {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            overflow: hidden;
            border: 3px solid var(--accent-purple);
            box-shadow: 0 0 15px rgba(187, 134, 252, 0.3);
            flex-shrink: 0;
        }

        .chibi-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .interactive-section {
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        button {
            background: linear-gradient(135deg, var(--bg-body), var(--accent-purple));
            color: var(--bg-body);
            font-weight: bold;
            border: none;
            padding: 12px 24px;
            font-size: 1rem;
            border-radius: 30px;
            cursor: pointer;
            transition: box-shadow 0.3s ease, transform 0.2s ease;
            margin-top: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        button:hover {
            box-shadow: 0 0 15px rgba(187, 134, 252, 0.7);
            transform: scale(1.05);
        }

        #mensaje-saludo {
            margin-top: 20px;
            font-size: 1.1rem;
            font-weight: 500;
            color: var(--accent-lila);
            min-height: 1.6em;
        }

        footer {
            margin-top: auto;
            text-align: center;
            padding: 30px;
            color: #5c4a79;
            font-size: 0.9rem;
            width: 100%;
        }

        @media (max-width: 600px) {
            .card {
                flex-direction: column;
                text-align: center;
            }
            .chibi-container {
                margin-bottom: 15px;
            }
            header h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>Luisa</h1>
        <p>Estudiante de Diseño Gráfico | Artista en progreso</p>
    </header>

    <main>
        <section class="card">
            <div class="chibi-container">
                <img src="https://i.pinimg.com/736x/8f/c1/c1/8fc1c12df3806a0904f46f56c738e411.jpg" alt="Suguru Geto Chibi Lindo" class="chibi-image">
            </div>
            <div class="card-content">
                <h2>Sobre mí</h2>
                <p>¡Hola! Soy Luisa. Actualmente estoy inmersa en el mundo del <strong>Diseño Gráfico</strong>, explorando la creatividad y formándome como una artista en constante progreso. Este sitio es un pequeño rincón para compartir mi camino.</p>
            </div>
        </section>

        <section class="card">
            <div class="card-content">
                <h2>Mis Pasiones</h2>
                <p>Más allá del diseño, estas son las cosas que me inspiran y me encantan:</p>
                <ul>
                    <li>El universo del <strong>Manga y el Anime</strong>.</li>
                    <li>La ilustración y la creación de personajes.</li>
                    <li>El amor y respeto por los <strong>Animales</strong>.</li>
                    <li>Explorar nuevas técnicas artísticas digitales.</li>
                </ul>
            </div>
        </section>

        <section class="card interactive-section">
            <div class="card-content">
                <h2>Un pequeño detalle</h2>
                <p>Haz clic abajo para recibir un saludo especial basado en tu hora actual:</p>
                <button id="saludo-btn">¡Generar Saludo!</button>
                <p id="mensaje-saludo"></p>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 - Creado con 💜 por Luisa para Actividad Práctica IV</p>
    </footer>

    <script>
        const boton = document.getElementById('saludo-btn');
        const mensaje = document.getElementById('mensaje-saludo');

        boton.addEventListener('click', () => {
            const horas = new Date().getHours();
            let saludoText = "";
            let emoji = "";
            
            if (horas >= 5 && horas < 12) {
                saludoText = "¡Buenos días, artista! Que tengas un día lleno de inspiración.";
                emoji = "🌅🎨";
            } else if (horas >= 12 && horas < 18) {
                saludoText = "¡Buenas tardes! Sigue creando cosas increíbles.";
                emoji = "☀️🖌️";
            } else {
                saludoText = "¡Buenas noches! Gracias por pasar por mi rincón creativo.";
                emoji = "🌌💜";
            }

            mensaje.textContent = `${emoji} ${saludoText}`;
            mensaje.style.opacity = 0;
            setTimeout(() => { mensaje.style.opacity = 1; mensaje.style.transition = "opacity 0.5s"; }, 50);
        });
    </script>

</body>
</html>

```
