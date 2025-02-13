<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi San Valentín?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            background-color: #ffcccb;
            font-family: Arial, sans-serif;
            text-align: center;
            overflow: hidden;
        }
        h1 {
            font-size: 2em;
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            font-size: 1.5em;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
        }
        .yes {
            background-color: #4CAF50;
            color: white;
        }
        .no {
            background-color: #f44336;
            color: white;
            position: absolute;
        }
        .hidden {
            display: none;
        }
    </style>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.3.5/dist/confetti.browser.min.js"></script>
</head>
<body>
    <script>
        function checkPassword() {
            let password = prompt("Ingresa la contraseña:");
            if (password !== "Lizbeth") {
                alert("Contraseña incorrecta. Intenta de nuevo.");
                checkPassword();
            }
        }
        checkPassword();
    </script>
    
    <h1>¿Quieres ser mi San Valentín? ❤️</h1>
    <div class="buttons">
        <button class="yes" onclick="yesClick()">Sí</button>
        <button class="no" id="noButton" onmouseover="moveButton()">No</button>
    </div>
    
    <div id="celebration" class="hidden">
        <img src="https://media.giphy.com/media/111ebonMs90YLu/giphy.gif" alt="Pandas felices">
    </div>

    <script>
        function yesClick() {
            alert("¡Sabía que dirías que sí! 💖");
            document.getElementById("celebration").classList.remove("hidden");
            confetti({
                particleCount: 100,
                spread: 70,
                origin: { y: 0.6 }
            });
        }

        function moveButton() {
            let button = document.getElementById("noButton");
            let x = Math.random() * (window.innerWidth - 100);
            let y = Math.random() * (window.innerHeight - 50);
            button.style.left = x + "px";
            button.style.top = y + "px";
        }
    </script>
</body>
</html>
