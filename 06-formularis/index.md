# 📝 Formularis i Validacions

## Què hem après fins ara?
Ja controlem:
- Els events i com gestionar-los
- La interacció amb l'usuari
- La modificació dinàmica d'elements

## Què aprendrem?
Aprendrem a treballar amb formularis HTML, recollir dades i validar-les abans d'enviar-les.

## Teoria
Els formularis són essencials per:
- Recollir dades dels usuaris
- Validar que les dades són correctes
- Evitar errors abans d'enviar

### Elements principals
- input (text, email, password, etc.)
- select (desplegables)
- textarea (text llarg)
- checkbox i radio
- submit (botó d'enviar)

## Exercici Pràctic
Anem a crear un formulari amb validacions!

1. Crea aquest arxiu HTML:

<!DOCTYPE html>
<html>
<head>
    <title>Formulari amb Validacions</title>
    <style>
        .error {
            color: red;
            font-size: 0.8em;
            display: none;
        }
        .input-error {
            border: 1px solid red;
        }
        .valid {
            border: 1px solid green;
        }
        form {
            max-width: 400px;
            margin: 20px auto;
            padding: 20px;
            border: 1px solid #ccc;
        }
        .form-group {
            margin-bottom: 15px;
        }
    </style>
</head>
<body>
    <form id="registre">
        <div class="form-group">
            <label for="nom">Nom:</label>
            <input type="text" id="nom" name="nom" required>
            <div id="error-nom" class="error">El nom ha de tenir almenys 3 caràcters</div>
        </div>

        <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            <div id="error-email" class="error">L'email no és vàlid</div>
        </div>

        <div class="form-group">
            <label for="edat">Edat:</label>
            <input type="number" id="edat" name="edat" required>
            <div id="error-edat" class="error">L'edat ha de ser entre 18 i 99</div>
        </div>

        <button type="submit">Enviar</button>
    </form>

    <script>
        const form = document.getElementById('registre');
        const nom = document.getElementById('nom');
        const email = document.getElementById('email');
        const edat = document.getElementById('edat');

        // Validació en temps real
        nom.addEventListener('input', function() {
            const errorNom = document.getElementById('error-nom');
            if (this.value.length < 3) {
                errorNom.style.display = 'block';
                this.classList.add('input-error');
                this.classList.remove('valid');
            } else {
                errorNom.style.display = 'none';
                this.classList.remove('input-error');
                this.classList.add('valid');
            }
        });

        // Validació del formulari complet
        form.addEventListener('submit', function(e) {
            let valid = true;

            // Validar nom
            if (nom.value.length < 3) {
                valid = false;
                document.getElementById('error-nom').style.display = 'block';
            }

            // Validar email
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailRegex.test(email.value)) {
                valid = false;
                document.getElementById('error-email').style.display = 'block';
            }

            // Validar edat
            const edatNum = parseInt(edat.value);
            if (edatNum < 18 || edatNum > 99) {
                valid = false;
                document.getElementById('error-edat').style.display = 'block';
            }

            if (!valid) {
                e.preventDefault();
            } else {
                alert('Formulari enviat correctament!');
            }
        });
    </script>
</body>
</html>

2. Obre l'arxiu al navegador
3. Prova d'introduir dades incorrectes i observa les validacions

## Repte
Modifica l'exemple per:
1. Afegir validació de contrasenya (mínim 8 caràcters, 1 majúscula, 1 número)
2. Afegir un camp de confirmació d'email
3. Crear un selector de província amb validació

## Per aprendre més
- Formularis HTML: https://developer.mozilla.org/ca/docs/Learn/Forms
- Validació de formularis: https://www.w3schools.com/js/js_validation.asp
- Expressions regulars: https://developer.mozilla.org/ca/docs/Web/JavaScript/Guide/Regular_Expressions

## Següent tema
Al següent tema veurem com treballar amb CSS i JavaScript junts, i quan utilitzar cada un. 