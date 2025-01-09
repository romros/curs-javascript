# 🚀 Introducció a JavaScript

## Què aprendrem?
En aquesta secció entendrem per què necessitem JavaScript i com complementa l'HTML i CSS que ja coneixem.

## Teoria
JavaScript és com la "intel·ligència" de les nostres pàgines web. Mentre que:
- HTML és l'estructura (com els ossos del cos)
- CSS és l'aparença (com la roba que portem)
- JavaScript és el comportament (com ens movem i interactuem)

### Exemples del món real
- Un formulari que valida les dades abans d'enviar-les
- Un joc simple al navegador
- Una aplicació web que actualitza dades sense recarregar la pàgina

## Exercici Pràctic
Anem a fer el nostre primer script!

1. Crea un arxiu HTML bàsic:

<!DOCTYPE html>
<html>
<head>
    <title>El meu primer JavaScript</title>
</head>
<body>
    <h1>Hola!</h1>
    <button id="boto">Fes clic aquí</button>

    <script>
        // El nostre codi JavaScript anirà aquí
        document.getElementById('boto').onclick = function() {
            alert('Hola! Has fet el teu primer JavaScript!');
        }
    </script>
</body>
</html>

2. Obre aquest arxiu al navegador
3. Fes clic al botó i veuràs el teu primer missatge JavaScript!

## Repte
Modifica l'exemple anterior perquè:
1. El botó canviï de color quan el cliques
2. El text del botó canviï després de fer-hi clic

## Per aprendre més
- JavaScript en català a SoftCatalà: https://www.softcatala.org/programari/javascript/
- Introducció a JavaScript a MDN (en castellà): https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Introduction
- Exercicis interactius a w3schools: https://www.w3schools.com/js/default.asp

## Següent tema
Al següent tema veurem el DOM, que ens permetrà interactuar amb els elements de la nostra pàgina web. 