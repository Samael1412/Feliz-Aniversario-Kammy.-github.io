<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz Aniversario, Kamyla</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@500&family=Great+Vibes&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #1a1a3d; /* Azul noche */
            color: #fff;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        /* Estrellas simuladas */
        .star {
            position: absolute;
            border-radius: 50%;
            background-color: #FFD700; /* Color amarillo */
            opacity: 0.7;
            animation: twinkle 1.5s infinite alternate;
            box-shadow: 0px 0px 8px rgba(255, 215, 0, 0.5); /* Efecto difuso */
        }

        /* Animación de parpadeo para las estrellas */
        @keyframes twinkle {
            0% {
                opacity: 0.3;
            }
            100% {
                opacity: 1;
            }
        }

        /* Efecto de estrellas: puntos amarillos dispersos por toda la página */
        .star-field {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            pointer-events: none;
        }

        .star-field .star {
            width: 4px;
            height: 4px;
            animation-duration: 2s;
        }

        .star-field .star:nth-child(odd) {
            animation-duration: 1.5s;
        }

        .star-field .star:nth-child(even) {
            animation-duration: 2.5s;
        }

        .container {
            background: rgba(255, 255, 255, 0.8);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.2);
            max-width: 500px;
            width: 90%;
            position: relative;
        }

        h1 {
            color: #ff6b6b;
            margin: 0;
            font-size: 2.5em;
            font-family: 'Dancing Script', cursive;
        }

        .date {
            color: #333;
            font-size: 1.2em;
            margin: 10px 0 20px;
        }

        .message {
            font-size: 1.2em;
            line-height: 1.6;
            margin: 20px 0;
        }

        .signature {
            font-size: 1.5em;
            color: #ff6b6b;
            margin-top: 20px;
        }

        /* Estilo para el botón con la imagen de pergamino ajustado */
        .play-button {
            background: url('https://raw.githubusercontent.com/Samael1412/Samael1412.github.io/main/tu-imagen.png') no-repeat center center;
            background-size: contain;  /* La imagen se ajustará sin perder calidad */
            width: 100px;  /* Ancho reducido del botón */
            height: 75px;  /* Alto del botón ajustado */
            color: #6A1B9A;  /* Color morado oscuro para mejor contraste */
            font-family: 'Great Vibes', cursive;
            font-size: 0.7em;  /* Tamaño del texto ajustado */
            border-radius: 10px;
            cursor: pointer;
            position: relative;
            display: flex;
            align-items: center;  /* Centra verticalmente el texto */
            justify-content: center;  /* Centra horizontalmente el texto */
            text-align: center;
            margin-top: 20px;
            border: none;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
            word-wrap: break-word;  /* Para que el texto se ajuste en dos líneas */
            line-height: 1.3;  /* Ajusta la altura de línea para mejorar la legibilidad */
        }

        .play-button:hover {
            transform: scale(1.1);
            box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.3);
        }

        .play-button:active {
            transform: scale(0.95);
        }

        .play-button::before {
            content: "✨";
            position: absolute;
            left: 10px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.5em; /* Tamaño de la estrella ajustado */
        }

        /* Estilo del audio oculto */
        audio {
            display: none;
        }

        /* Corazones decorativos */
        .heart-icon {
            font-size: 1.5em;
            color: #ff6b6b;
            margin: 0 10px;
        }
    </style>
</head>
<body>

<!-- Campo de estrellas -->
<div class="star-field">
    <!-- Estrellas generadas aleatoriamente con mayor densidad -->
    <div class="star" style="top: 5%; left: 15%;"></div>
    <div class="star" style="top: 10%; left: 30%;"></div>
    <div class="star" style="top: 15%; left: 60%;"></div>
    <div class="star" style="top: 20%; left: 80%;"></div>
    <div class="star" style="top: 25%; left: 40%;"></div>
    <div class="star" style="top: 50%; left: 70%;"></div>
    <div class="star" style="top: 60%; left: 20%;"></div>
    <div class="star" style="top: 80%; left: 90%;"></div>
    <div class="star" style="top: 90%; left: 50%;"></div>
</div>

<!-- Contenedor central -->
<div class="container">
    <h1>Feliz Aniversario, Kamyla</h1>
    <p class="date">14 de Noviembre de 2024</p>
    <p class="message">
        Mi querida Kamyla, te deseo un maravilloso y brillante aniversario.
        Que nuestra historia de amor continúe creciendo con cada día.
    </p>
    <div class="signature">Con todo mi amor, Samael</div>

    <audio id="audio" loop>
        <source src="[https://raw.githubusercontent.com/Samael1412/Samael1412.github.io/main/tu-archivo-de-musica.mp3](https://github.com/Samael1412/Samael1412.github.io/blob/main/Stromae%2C%20Pomme%20-%20Ma%20Meilleure%20Ennemie%20l%20(Arcane%20Season%202%20looped.mp3)" type="audio/mp3">
        Tu navegador no soporta el formato de audio.
    </audio>

    <button class="play-button" onclick="playPauseAudio()">Haz clic aquí <br> para la magia ✨</button>
</div>

<script>
    var audio = document.getElementById('audio');

    function playPauseAudio() {
        if (audio.paused) {
            audio.play();
        } else {
            audio.pause();
        }
    }
</script>

</body>
</html>

