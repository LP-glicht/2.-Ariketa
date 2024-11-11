<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>1. Ariketa</title>
    <style>
        body { font-family: Arial, sans-serif; color: #141212dd;background-color: rgb(172, 241, 241);}
        h1 { text-align: center; color: #0f7c79; }
        h2 { font-size:20px; color: black}
        nav a { font-weight:bold; color: blue}
    </style>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
    <script src='main.js'></script>
</head>
<body>
  <nav>
    <a href="Lehena.html"> NBA </a>
    <a href="Bigarrena.html"> Irudiak </a>
    <a href="Hirugarrena.html"> Jokalaria </a>
  </nav>
  <html lang="es">
<head>
  <html lang="eu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NBAri Buruzko Azterketa - EPIKOA!</title>
    <style>
        /* Estilo orokorra */
        body {
            font-family: 'Arial', sans-serif;
            color: #333;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }
        header {
            background-color: #1d428a;
            color: #fff;
            padding: 20px;
            text-align: center;
            font-size: 2em;
            letter-spacing: 2px;
        }
        h1 {
            color: #ef3a42;
            text-shadow: 2px 2px #1d428a;
        }
        h2, h3 {
            color: #1d428a;
            transition: color 0.3s, transform 0.3s;
            text-align: center;
        }
        h2:hover, h3:hover {
            color: #ef3a42;
            transform: scale(1.1);
        }
        .container {
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        .highlight {
            color: #ef3a42;
            font-weight: bold;
        }
        /* Jokoaren estiloa */
        #snake-game {
            width: 500px;
            height: 500px;
            margin: 20px auto;
            border: 5px solid #ef3a42;
            position: relative;
            background-color: #1d428a;
        }
        #snake-game canvas {
            width: 100%;
            height: 100%;
        }
        .message {
            color: #fff;
            font-size: 2em;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            display: none;
        }
        .button {
            display: inline-block;
            background-color: #ef3a42;
            color: #fff;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s;
            cursor: pointer;
            margin-top: 20px;
        }
        .button:hover {
            background-color: #1d428a;
        }
    </style>
    <script>
        // Snake joko hobetua
        document.addEventListener('DOMContentLoaded', function () {
            const canvas = document.getElementById('snakeCanvas');
            const ctx = canvas.getContext('2d');
            const box = 20;
            let score = 0;
            let snake = [{x: 10 * box, y: 10 * box}];
            let food = {
                x: Math.floor(Math.random() * 24) * box,
                y: Math.floor(Math.random() * 24) * box
            };
            let direction;
            const gameSize = 500;

            // Elikadura egiteko norabidea
            document.addEventListener("keydown", changeDirection);

            function changeDirection(event) {
                if (event.keyCode == 37 && direction != "RIGHT") direction = "LEFT";
                else if (event.keyCode == 38 && direction != "DOWN") direction = "UP";
                else if (event.keyCode == 39 && direction != "LEFT") direction = "RIGHT";
                else if (event.keyCode == 40 && direction != "UP") direction = "DOWN";
            }

            function collision(newHead, snake) {
                for (let i = 0; i < snake.length; i++) {
                    if (newHead.x == snake[i].x && newHead.y == snake[i].y) {
                        return true;
                    }
                }
                return false;
            }

            function draw() {
                ctx.fillStyle = "#1d428a";
                ctx.fillRect(0, 0, gameSize, gameSize);

                for (let i = 0; i < snake.length; i++) {
                    ctx.fillStyle = i === 0 ? "#ef3a42" : "#f4f4f9";
                    ctx.fillRect(snake[i].x, snake[i].y, box, box);
                    ctx.strokeStyle = "#1d428a";
                    ctx.strokeRect(snake[i].x, snake[i].y, box, box);
                }

                // Janaria marraztu
                ctx.fillStyle = "yellow";
                ctx.fillRect(food.x, food.y, box, box);

                let snakeX = snake[0].x;
                let snakeY = snake[0].y;

                if (direction == "LEFT") snakeX -= box;
                if (direction == "UP") snakeY -= box;
                if (direction == "RIGHT") snakeX += box;
                if (direction == "DOWN") snakeY += box;

                if (snakeX == food.x && snakeY == food.y) {
                    score++;
                    food = {
                        x: Math.floor(Math.random() * 24) * box,
                        y: Math.floor(Math.random() * 24) * box
                    };
                } else {
                    snake.pop();
                }

                let newHead = {x: snakeX, y: snakeY};

                if (snakeX < 0 || snakeY < 0 || snakeX >= gameSize || snakeY >= gameSize || collision(newHead, snake)) {
                    clearInterval(game);
                    document.getElementById('lose-message').style.display = "block";
                }

                snake.unshift(newHead);

                ctx.fillStyle = "white";
                ctx.font = "20px Arial";
                ctx.fillText("Puntuazioa: " + score, 10, gameSize - 10);
            }

            let game = setInterval(draw, 100);
        });
    </script>
</head>
<body>

<header>
    <h1>NBAri Buruzko Azterketa 🏀 EPIKOA!</h1>
    <p>Ongi etorri NBAko mundu zirraragarrira!</p>
</header>

<div class="container">
    <section>
        <h2>NBAren Historia Laburra</h2>
        <p><span class="highlight">NBA</span> (National Basketball Association) 1946an sortu zen eta ordutik mundu osoan milioika jarraitzaile ditu. Gaur egun, 30 talde ditu, historia, talentua eta ikuskizunaren nahasketa perfektua da. Munduko saskibaloi ligarik ospetsuena da!</p>
    </section>

    <section>
        <h2>Jokalari Mitikoak</h2>
        <div class="player-card">
            <h3>Michael Jordan</h3>
            <p>Denborarik onenaren jokalari bezala aitortua, MJ-k 6 txapelketa irabazi zituen Chicago Bullsekin eta saskibaloia iraultzea lortu zuen.</p>
            <button class="button" onclick="toggleImage('mjImage')">Irudia ikusi</button>
            <img id="mjImage" src="https://upload.wikimedia.org/wikipedia/commons/8/8d/Michael_Jordan_in_2014.jpg" alt="Michael Jordan">
        </div>

        <div class="player-card">
            <h3>LeBron James</h3>
            <p>Belaunaldi bakoitzean halako jokalari bat bakarrik egoten da, LeBronek hiru talde ezberdinekin txapelketak irabazi ditu eta historiak idazten jarraitzen du.</p>
            <button class="button" onclick="toggleImage('lebronImage')">Irudia ikusi</button>
            <img id="lebronImage" src="https://upload.wikimedia.org/wikipedia/commons/7/76/LeBron_James_2019.jpg" alt="LeBron James">
        </div>
    </section>

    <section>
        <h2>SNAKE JOKOA - Jokalari Mitikoen Erreflexuak Bezala!</h2>
        <div id="snake-game">
            <canvas id="snakeCanvas" width="500" height="500"></canvas>
            <div id="lose-message" class="message">Jokoa Galdu Duzu 😢</div>
        </div>
        <button class="button" onclick="window.location.reload()">Berriro Jokatu</button>
    </section>
</div>

</body>
</html># 2.-Ariketa
