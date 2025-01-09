# 🌳 El DOM: La nostra finestra al document

## Què aprendrem?
Entendrem què és el DOM (Document Object Model) i com ens permet interactuar amb els elements de la nostra pàgina web.

## Teoria
El DOM és com un arbre familiar dels elements HTML:
- La pàgina (document) és l'arrel
- Cada element HTML és una branca (node)
- Els elements dins d'altres elements són fills
- El text i atributs són les fulles

### Conceptes clau
- Cada element és un objecte que podem manipular
- Els elements tenen propietats (com style, innerHTML)
- Els elements tenen relacions (pare, fill, germà)

## Exercici Pràctic
Anem a explorar el DOM!

1. Crea aquest arxiu HTML:

<!DOCTYPE html>
<html>
<head>
    <title>Explorant el DOM</title>
</head>
<body>
    <div id="contenidor">
        <h1>Hola DOM!</h1>
        <p>Aquest és un paràgraf</p>
        <ul>
            <li>Element 1</li>
            <li>Element 2</li>
        </ul>
    </div>

    <script>
        // Veiem l'estructura
        console.log(document.getElementById('contenidor'));
        
        // Veiem els fills
        const contenidor = document.getElementById('contenidor');
        console.log(contenidor.children);
        
        // Veiem el pare d'un element
        const paragraf = document.querySelector('p');
        console.log(paragraf.parentElement);
    </script>
</body>
</html>

2. Obre les eines de desenvolupador del navegador (F12)
3. Mira la consola per veure l'estructura

## Repte
Modifica l'exemple per:
1. Trobar i mostrar tots els elements 'li'
2. Canviar el text del primer 'li'
3. Afegir un nou 'li' a la llista

## Per aprendre més
- Guia del DOM a MDN (català): https://developer.mozilla.org/ca/docs/Web/API/Document_Object_Model/Introduction
- Visualitzador del DOM: https://software.hixie.ch/utilities/js/live-dom-viewer/
- Exercicis DOM: https://www.w3schools.com/js/js_htmldom.asp

## Següent tema
Al següent tema aprendrem a seleccionar elements específics del DOM utilitzant diferents mètodes. 