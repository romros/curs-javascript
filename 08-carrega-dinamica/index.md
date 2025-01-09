# 🔄 Càrrega Dinàmica: Actualitzant Contingut sense Recarregar

## Què hem après fins ara?
Ja dominem:
- Tot el relacionat amb el DOM
- Events i interaccions
- Formularis i validacions
- Quan usar JavaScript vs CSS

## Què aprendrem?
Aprendrem com podem actualitzar parts de la nostra pàgina sense necessitat de recarregar-la sencera, fent-la més ràpida i agradable d'usar.

## Teoria
La càrrega dinàmica ens permet:
- Actualitzar només el contingut necessari
- Mantenir la resta de la pàgina intacta
- Millorar l'experiència d'usuari
- Estalviar dades i temps de càrrega

### Conceptes bàsics
- fetch: per demanar dades al servidor
- Promeses: per gestionar respostes
- JSON: format de dades més comú

## Exercici Pràctic
Anem a crear un exemple simple de càrrega dinàmica!

1. Crea aquest arxiu HTML:

<!DOCTYPE html>
<html>
<head>
    <title>Càrrega Dinàmica</title>
    <style>
        .contenidor {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            border: 1px solid #ccc;
        }
        .loading {
            display: none;
            color: blue;
        }
    </style>
</head>
<body>
    <div class="contenidor">
        <h1>Notícies</h1>
        <button id="carregaNoticies">Carregar Notícies</button>
        <p id="loading" class="loading">Carregant...</p>
        <div id="noticies"></div>
    </div>

    <script>
        const boto = document.getElementById('carregaNoticies');
        const loading = document.getElementById('loading');
        const noticies = document.getElementById('noticies');

        // Simular una API de notícies
        const getNoticies = () => {
            return new Promise(resolve => {
                setTimeout(() => {
                    resolve([
                        { titol: "Nova versió de JavaScript", text: "ES2024 porta noves funcionalitats..." },
                        { titol: "CSS Grid revoluciona el disseny web", text: "Els desenvolupadors adopten..." },
                        { titol: "El DOM és més fàcil que mai", text: "Noves APIs simplifiquen..." }
                    ]);
                }, 1500); // Simulem un retard de 1.5 segons
            });
        };

        boto.addEventListener('click', async function() {
            // Mostrem loading
            loading.style.display = 'block';
            boto.disabled = true;

            try {
                // Obtenim les notícies
                const dades = await getNoticies();
                
                // Creem el contingut
                const html = dades.map(noticia => `
                    <article>
                        <h3>${noticia.titol}</h3>
                        <p>${noticia.text}</p>
                    </article>
                `).join('');

                // Actualitzem la pàgina
                noticies.innerHTML = html;
            } catch (error) {
                noticies.innerHTML = 'Error carregant les notícies';
            } finally {
                // Amaguem loading
                loading.style.display = 'none';
                boto.disabled = false;
            }
        });
    </script>
</body>
</html>

2. Obre l'arxiu al navegador
3. Fes clic al botó i observa com es carreguen les notícies sense recarregar la pàgina

## Repte
Modifica l'exemple per:
1. Afegir més tipus de contingut (comentaris, likes...)
2. Implementar un botó per esborrar les notícies
3. Afegir animacions quan apareixen les notícies

## Per aprendre més
- Fetch API: https://developer.mozilla.org/ca/docs/Web/API/Fetch_API
- Async/Await: https://developer.mozilla.org/ca/docs/Web/JavaScript/Reference/Statements/async_function
- JSON: https://developer.mozilla.org/ca/docs/Web/JavaScript/Reference/Global_Objects/JSON

## Fi del Curs
Felicitats! Has completat tots els temes del curs. Ara ja saps:
- Manipular el DOM
- Treballar amb events
- Validar formularis
- Distingir entre CSS i JavaScript
- Carregar contingut dinàmicament

Recorda que la pràctica és la clau per millorar. Segueix experimentant i creant! 