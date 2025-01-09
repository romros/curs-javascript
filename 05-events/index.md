# 🎮 Events: Fent la Pàgina Interactiva

## Què hem après fins ara?
Ja dominem:
- La selecció d'elements
- La modificació del contingut
- El canvi d'estils i classes

## Què aprendrem?
Aprendrem com detectar i respondre a les accions de l'usuari (clics, tecles, moviments del ratolí, etc.) utilitzant esdeveniments.

## Teoria
Els events són com "sensors" que detecten accions:
- Ratolí: click, dblclick, mouseover, mouseout
- Teclat: keydown, keyup, keypress
- Formulari: submit, change, focus, blur
- Document: load, DOMContentLoaded
- Finestra: resize, scroll

### Formes d'utilitzar events
1. Mètode modern: addEventListener()
2. Propietat onclick (menys recomanat)
3. Atribut HTML onclick (no recomanat)

## Exercici Pràctic
Anem a crear una pàgina interactiva!

1. Crea aquest arxiu HTML:

<!DOCTYPE html>
<html>
<head>
    <title>Treballant amb Events</title>
    <style>
        .caixa {
            width: 200px;
            height: 200px;
            background-color: lightblue;
            margin: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .actiu {
            background-color: lightgreen;
        }
    </style>
</head>
<body>
    <div class="caixa" id="caixa1">Passa per sobre!</div>
    <div class="caixa" id="caixa2">Fes doble clic!</div>
    <input type="text" id="entrada" placeholder="Escriu aquí...">
    <p id="comptador">Tecles premudes: 0</p>

    <script>
        const caixa1 = document.getElementById('caixa1');
        const caixa2 = document.getElementById('caixa2');
        const entrada = document.getElementById('entrada');
        const comptador = document.getElementById('comptador');
        let compteTecles = 0;

        // Event mouseover/mouseout
        caixa1.addEventListener('mouseover', function() {
            this.classList.add('actiu');
            this.textContent = "Dins!";
        });

        caixa1.addEventListener('mouseout', function() {
            this.classList.remove('actiu');
            this.textContent = "Passa per sobre!";
        });

        // Event doble clic
        caixa2.addEventListener('dblclick', function() {
            this.textContent = "Doble clic detectat!";
            setTimeout(() => {
                this.textContent = "Fes doble clic!";
            }, 1000);
        });

        // Events de teclat
        entrada.addEventListener('keyup', function() {
            compteTecles++;
            comptador.textContent = `Tecles premudes: ${compteTecles}`;
        });
    </script>
</body>
</html>

2. Obre l'arxiu al navegador
3. Interactua amb els elements i observa com responen

## Repte
Modifica l'exemple per:
1. Afegir un event de clic dret (contextmenu)
2. Crear un comptador de clics per cada caixa
3. Mostrar quina tecla s'ha premut a l'input

## Per aprendre més
- Events DOM a MDN: https://developer.mozilla.org/ca/docs/Web/API/Event
- Llista completa d'events: https://developer.mozilla.org/en-US/docs/Web/Events
- Tutorial interactiu: https://www.w3schools.com/js/js_events.asp

## Següent tema
Al següent tema veurem com treballar amb formularis i validar les dades abans d'enviar-les. 