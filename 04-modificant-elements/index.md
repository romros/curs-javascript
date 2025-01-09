# ✨ Modificant Elements del DOM

## Què hem après fins ara?
Ja sabem:
- Com funciona el DOM
- Com seleccionar elements
- Els diferents tipus de selectors

## Què aprendrem?
Aprendrem com canviar elements HTML dinàmicament: el seu contingut, estils, classes i atributs.

## Teoria
Podem modificar diferents aspectes dels elements:
- Contingut: .textContent, .innerHTML
- Estils: .style
- Classes: .classList
- Atributs: .setAttribute(), .getAttribute()

### Mètodes principals
- textContent: canvia només el text
- innerHTML: canvia el contingut HTML
- style: modifica estils directament
- classList: afegeix/elimina classes
- setAttribute: modifica atributs

## Exercici Pràctic
Anem a modificar elements!

1. Crea aquest arxiu HTML:

<!DOCTYPE html>
<html>
<head>
    <title>Modificant Elements</title>
    <style>
        .destacat { 
            background-color: yellow; 
            padding: 10px;
        }
        .gran { 
            font-size: 24px; 
            color: blue;
        }
    </style>
</head>
<body>
    <div id="contenidor">
        <h1 id="titol">Hola DOM!</h1>
        <p id="text">Aquest text canviarà</p>
        <button id="boto1">Canvia Text</button>
        <button id="boto2">Canvia Estil</button>
        <button id="boto3">Afegeix Classe</button>
    </div>

    <script>
        // Elements
        const titol = document.getElementById('titol');
        const text = document.getElementById('text');
        const boto1 = document.getElementById('boto1');
        const boto2 = document.getElementById('boto2');
        const boto3 = document.getElementById('boto3');

        // Esdeveniments
        boto1.onclick = function() {
            text.textContent = "Text modificat!";
            titol.innerHTML = "Nou <em>títol</em> modificat!";
        };

        boto2.onclick = function() {
            text.style.color = 'red';
            text.style.backgroundColor = '#f0f0f0';
        };

        boto3.onclick = function() {
            text.classList.toggle('destacat');
            titol.classList.toggle('gran');
        };
    </script>
</body>
</html>

2. Obre l'arxiu al navegador
3. Prova els diferents botons i observa els canvis

## Repte
Modifica l'exemple per:
1. Afegir un botó que canviï múltiples estils alhora
2. Crear un botó que afegeixi un nou element HTML
3. Fer que el text mostri quantes vegades s'ha clicat cada botó

## Per aprendre més
- Manipulació DOM MDN: https://developer.mozilla.org/ca/docs/Web/API/Document_Object_Model/Introduction
- Guia d'estils JavaScript: https://www.w3schools.com/js/js_htmldom_css.asp
- Tutorial interactiu: https://www.codecademy.com/learn/introduction-to-javascript

## Següent tema
Al següent tema veurem els esdeveniments (events) i com podem fer que la nostra pàgina respongui a les accions de l'usuari. 