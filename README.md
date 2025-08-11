<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Juego del Ahorcado</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Juego del Ahorcado</h1>
  <div id="game">
    <p id="word"></p>
    <p>Letras usadas: <span id="used-letters"></span></p>
    <p>Intentos restantes: <span id="attempts"></span></p>
    <input type="text" id="letter-input" maxlength="1" autofocus>
    <button onclick="guessLetter()">Adivinar letra</button>
    <p id="message"></p>
    <button id="restart-btn" onclick="startGame()" style="display:none;">Jugar de nuevo</button>
  </div>
  <script src="app.js"></script>
</body>
</html>
