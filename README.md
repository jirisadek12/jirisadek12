

```html
<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Karkuláček - jednoduchá hra</title>
    <style>
        body { font-family: Arial, sans-serif; }
        #game { width: 600px; height: 400px; border: 1px solid #000; position: relative; overflow: hidden; }
        .player { width: 50px; height: 50px; background-color: red; position: absolute; }
    </style>
</head>
<body>
    <h1>Karkuláček</h1>
    <div id="game">
        <div class="player" id="karkulka"></div>
    </div>
    <button onclick="moveKarkulka('left')">Doleva</button>
    <button onclick="moveKarkulka('right')">Doprava</button>
    <button onclick="moveKarkulka('up')">Nahoru</button>
    <button onclick="moveKarkulka('down')">Dolu</button>

    <script>
        const karkulka = document.getElementById('karkulka');
        let position = { x: 0, y: 0 };

        function moveKarkulka(direction) {
            const step = 10; // velikost pohybu

            switch (direction) {
                case 'left':
                    position.x -= step; break;
                case 'right':
                    position.x += step; break;
                case 'up':
                    position.y -= step; break;
                case 'down':
                    position.y += step; break;
            }

            // omezení pohybu v rámci herního pole
            position.x = Math.max(0, Math.min(position.x, 550));
            position.y = Math.max(0, Math.min(position.y, 350));

            karkulka.style.transform = `translate(${position.x}px, ${position.y}px)`;
        }
    </script>
</body>
</html>
```


