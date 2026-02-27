<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Tengo una pregunta... ❤️</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        body {
            display: flex; justify-content: center; align-items: center; height: 100vh;
            background-color: #ffe6f2; font-family: sans-serif; overflow: hidden;
            position: relative; overscroll-behavior: none;
        }
        .container { text-align: center; width: 100%; z-index: 1; padding: 20px; }
        .gif-img { width: 100%; max-width: 250px; border-radius: 15px; margin-bottom: 20px; }
        h1 { font-size: 1.8rem; color: #d63384; margin-bottom: 30px; }
        .btns { display: flex; justify-content: center; gap: 20px; height: 50px; }
        .btn {
            border: none; border-radius: 50px; padding: 15px 30px; font-size: 18px;
            font-weight: bold; background-color: #ff54a4; color: white;
            box-shadow: 0 5px 15px rgba(255, 84, 164, 0.3); touch-action: none;
        }
        #btn-no { position: absolute; z-index: 999; transition: 0.1s; }
        .hidden { display: none !important; }
    </style>
</head>
<body>
    <div class="container">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueW9oZ3M0eXF4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4JnB0PWEmZXA9djFfaW50ZXJuYWxfZ2lmX2J5X2lkJmN0PWc/c76IJLufpNwSULPk77/giphy.gif" class="gif-img" id="main-gif">
        <h1 id="main-text">¿Quieres ser mi novia? ❤️</h1>
        <div class="btns">
            <button class="btn" id="btn-yes">¡SÍ!</button>
            <button class="btn" id="btn-no">No</button>
        </div>
    </div>

    <script>
        const btnNo = document.getElementById('btn-no');
        const btnYes = document.getElementById('btn-yes');

        function mover(e) {
            if(e) e.preventDefault();
            const maxX = window.innerWidth - btnNo.offsetWidth - 20;
            const maxY = window.innerHeight - btnNo.offsetHeight - 20;
            const x = Math.max(10, Math.random() * maxX);
            const y = Math.max(10, Math.random() * maxY);
            
            btnNo.style.position = 'fixed';
            btnNo.style.left = x + 'px';
            btnNo.style.top = y + 'px';

            // Intenta vibrar el Honor (si tiene permiso)
            if (navigator.vibrate) navigator.vibrate(50);
        }

        btnNo.addEventListener('touchstart', mover, {passive: false});
        btnNo.addEventListener('pointerdown', mover);
        btnNo.addEventListener('click', mover);

        btnYes.addEventListener('click', () => {
            document.getElementById('main-text').innerHTML = "¡SABÍA QUE DIRÍAS QUE SÍ! 😍";
            document.getElementById('main-gif').src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueW9oZ3M0eXF4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4JnB0PWEmZXA9djFfaW50ZXJuYWxfZ2lmX2J5X2lkJmN0PWc/MDJ9Ibh3vUzS0/giphy.gif";
            btnNo.style.display = 'none';
            btnYes.style.display = 'none';
        });
    </script>
</body>
</html>
