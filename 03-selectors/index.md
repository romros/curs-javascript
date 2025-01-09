# 🎯 Seleccionant Elements del DOM

## Què aprendrem?
Aprendrem les diferents maneres de trobar i seleccionar elements HTML dins del nostre document utilitzant JavaScript.

## Teoria
Hi ha diverses maneres de seleccionar elements:
- Per ID: document.getElementById('id-unic')
- Per classe: document.getElementsByClassName('classe')
- Per etiqueta: document.getElementsByTagName('div')
- Amb querySelector: document.querySelector('.classe')
- Amb querySelectorAll: document.querySelectorAll('p')

### Diferències importants
- getElementById retorna UN element
- getElementsByClassName retorna una COL·LECCIÓ d'elements
- querySelector retorna el PRIMER element que troba
- querySelectorAll retorna TOTS els elements que coincideixen

## Exercici Pràctic
Anem a practicar amb els selectors!

1. Crea aquest arxiu HTML:

<!DOCTYPE html>
<html>
<head>
    <title>Practicant Selectors</title>
</head>
<body>
    <div id="principal">
        <h1 class="titol">Selectors en JavaScript</h1>
        <p class="text">Aquest és el primer paràgraf</p>
        <p class="text destacat">Aquest és un paràgraf destacat</p>
        <ul>
            <li class="item">Element 1</li>
            <li class="item">Element 2</li>
            <li class="item destacat">Element 3</li>
        </ul>
    </div>

    <script>
        // Diferents maneres de seleccionar
        const principal = document.getElementById('principal');
        const titol = document.querySelector('.titol');
        const textos = document.getElementsByClassName('text');
        const items = document.querySelectorAll('.item');
        const destacat = document.querySelectorAll('.destacat');

        // Mostrem els resultats
        console.log('Principal:', principal);
        console.log('Títol:', titol);
        console.log('Textos:', textos);
        console.log('Items:', items);
        console.log('Destacats:', destacat);
    </script>
</body>
</html>

2. Obre les eines de desenvolupador (F12)
3. Mira la consola per veure què retorna cada selector

## Repte
Modifica l'exemple per:
1. Trobar només el primer element amb classe 'destacat'
2. Canviar el color de tots els elements 'item'
3. Afegir la classe 'destacat' al primer paràgraf

## Per aprendre més
- Selectors a MDN (català): https://developer.mozilla.org/ca/docs/Web/API/Document/querySelector
- Guia de selectors CSS: https://www.w3schools.com/cssref/css_selectors.asp
- Joc per practicar selectors: https://flukeout.github.io/

## Següent tema
Al següent tema veurem com modificar els elements que hem seleccionat: canviar contingut, estils i atributs. 