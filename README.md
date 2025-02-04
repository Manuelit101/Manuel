<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animación de Disparo</title>
    <style>
        body {
            background-color: black;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }
        .container {
            position: relative;
        }
        .gun {
            width: 150px;
            height: auto;
        }
        .bullet {
            position: absolute;
            width: 20px;
            height: 5px;
            background-color: yellow;
            top: 50%;
            left: 150px;
            display: none;
        }
        @keyframes shoot {
            0% { transform: translateX(0); opacity: 1; }
            100% { transform: translateX(500px); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="container">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR1O0o0bzP5351MuwGgn8H-oR1j2GNsz7lYCQ&s" class="gun">
        <div class="bullet"></div>
    </div>
    <audio id="gunshot" src="https://www.fesliyanstudios.com/play-mp3/4382"></audio>
    <script>
        document.body.addEventListener("click", function() {
            let bullet = document.querySelector(".bullet");
            let gunshot = document.getElementById("gunshot");
            bullet.style.display = "block";
            bullet.style.animation = "shoot 0.5s linear forwards";
            gunshot.play();
            setTimeout(() => {
                bullet.style.display = "none";
                bullet.style.animation = "none";
            }, 500);
        });
    </script>
</body>
</html>
