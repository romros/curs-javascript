# ⚔️ JavaScript vs CSS: Quan Utilitzar Cada Un

## Què hem après fins ara?
Ja sabem treballar amb:
- Formularis i validacions
- Events i interaccions
- Modificacions del DOM

## Què aprendrem?
Aprendrem a distingir quan és millor utilitzar CSS i quan és millor utilitzar JavaScript per a diferents tipus d'interaccions i efectes.

## Teoria
Cada tecnologia té el seu propòsit:

CSS és millor per:
- Estils i aparença
- Animacions simples
- Hover effects
- Responsive design
- Transicions

JavaScript és millor per:
- Interaccions complexes
- Validacions
- Càlculs i lògica
- Modificacions dinàmiques
- Comunicació amb el servidor

## Exercici Pràctic
Anem a comparar les dues aproximacions!

1. Crea aquest arxiu HTML:

<!DOCTYPE html>
<html>
<head>
    <title>CSS vs JavaScript</title>
    <style>
        .boto-css {
            padding: 10px 20px;
            background-color: blue;
            color: white;
            border: none;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .boto-css:hover {
            background-color: darkblue;
            transform: scale(1.1);
        }

        .boto-js {
            padding: 10px 20px;
            background-color: green;
            color: white;
            border: none;
            cursor: pointer;
        }

        .menu {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }

        .menu.obert {
            max-height: 200px;
        }

        .exemple {
            margin: 20px;
            padding: 20px;
            border: 1px solid #ccc;
        }
    </style>
</head>
<body>
    <div class="exemple">
        <h3>Efecte Hover</h3>
        <button class="boto-css">Hover amb CSS</button>
        <button class="boto-js" id="botoJS">Hover amb JS</button>
    </div>

    <div class="exemple">
        <h3>Menú Desplegable</h3>
        <button onclick="toggleMenu('menuCSS')">Menú CSS</button>
        <div id="menuCSS" class="menu">
            <p>Opció 1</p>
            <p>Opció 2</p>
            <p>Opció 3</p>
        </div>

        <button onclick="toggleMenuJS('menuJS')">Menú JavaScript</button>
        <div id="menuJS" style="display: none;">
            <p>Opció 1</p>
            <p>Opció 2</p>
            <p>Opció 3</p>
        </div>
    </div>

    <script>
        // Efecte hover amb JavaScript
        const botoJS = document.getElementById('botoJS');
        
        botoJS.addEventListener('mouseenter', function() {
            this.style.backgroundColor = 'darkgreen';
            this.style.transform = 'scale(1.1)';
        });

        botoJS.addEventListener('mouseleave', function() {
            this.style.backgroundColor = 'green';
            this.style.transform = 'scale(1)';
        });

        // Menú amb CSS
        function toggleMenu(id) {
            document.getElementById(id).classList.toggle('obert');
        }

        // Menú amb JavaScript
        function toggleMenuJS(id) {
            const menu = document.getElementById(id);
            if (menu.style.display === 'none') {
                menu.style.display = 'block';
            } else {
                menu.style.display = 'none';
            }
        }
    </script>
</body>
</html>

2. Obre l'arxiu al navegador
3. Compara els dos mètodes i observa les diferències

## Repte
Modifica l'exemple per:
1. Crear una animació de rotació amb CSS i la mateixa amb JavaScript
2. Implementar un acordió amb les dues tècniques
3. Fer un efecte de fade-in amb CSS i JavaScript

## Per aprendre més
- CSS Animations: https://developer.mozilla.org/ca/docs/Web/CSS/CSS_Animations
- JavaScript Animations: https://www.w3schools.com/js/js_animations.asp
- CSS vs JS Performance: https://developer.mozilla.org/en-US/docs/Web/Performance/CSS_JavaScript_animation_performance

## Següent tema
Al següent tema veurem com carregar contingut dinàmicament sense recarregar la pàgina. 