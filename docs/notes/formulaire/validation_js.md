# Validation de formulaire en Javascript

Il y a plusieurs méthode pour valider nos formulaire en Javascript. Nous allons nous en tenir à deux méthodes qui se rapproche de ce qu'on fait déjà en utilisant l'action submit du formulaire. L'avantage majeur d'utiliser Javascript est que ça nous permet de faire une validation beaucoup plus précise et efficace.

## onsubmit

La première méthode est d'utiliser `onsubmit` dans la balise **form** pour appeler une fonction Javascript lors du "submit" du formulaire. La fonction doit être appeler de la façon suivante et retourner true ou false : 

**HTML**

``````html
<form id="mon-formulaire"
    action="traitement.php" 
    method="post" 
    onsubmit="return ValidationOnSubmit()">
``````

**Javascript**

``````js
function ValidationOnSubmit() 
{
    let formValide = false;
    
    // Traitement de validation

    return formValide;
}
``````

Un retour de la valeur false va empêcher le submit et une valeur true va au contraire l'autoriser.

## preventDefault

La seconde méthode est d'utiliser la méthode `preventDefault` associée au formulaire pour bloqué le comportement du "submit" et ensuite faire notre validation.  La fonction de validation sera appelé quand l'événement submit de notre formulaire sera déclenché. On utilisera un addEventListener pour ce faire. Dans la fonction associée à l'événement, on commence par annuler l'envoi avec `preventDefault`. Une fois la validation effectuée, on peut relancer un submit depuis notre script.

``````js
const monFormulaire = document.getElementById("mon-formulaire")
monFormulaire.addEventListener('submit', ValidationFormulaire);

function ValidationFormulaire(e) 
{
    // Annule le comportement par défaut du submit
    e.preventDefault();
    // Initialise une variable qui détermine si le 
    // formulaire doit être envoyé ou non
    let formValide = false;

    // Traitement de validation
    // Le code de validation va se retrouver ici

    // Si notre variable est vrai, on envoi le formulaire
    if (formValide) {
        // On relance un submit
        monFormulaire.submit();
    }
}
``````

## Références

- [https://developer.mozilla.org/fr/docs/Learn/Forms/Form_validation](https://developer.mozilla.org/fr/docs/Learn/Forms/Form_validation){target=_blank}
- [https://www.tutorialspoint.com/javascript/javascript_form_validations.htm](https://www.tutorialspoint.com/javascript/javascript_form_validations.htm){target=_blank}
- [https://www.javascripttutorial.net/javascript-dom/javascript-form-validation/](https://www.javascripttutorial.net/javascript-dom/javascript-form-validation/){target=_blank}
- [https://www.w3schools.com/js/js_validation.asp](https://www.w3schools.com/js/js_validation.asp){target=_blank}

## Valider un texte selon une expression régulière

On peut utiliser une expression régulière pour tester si un texte correspond à un certain format, comme une adresse courriel par exemple. Un variable ou un string l'expression régulière suivie de la fonction `.test()` avec le texte en paramètre retournera **true** si le texte correspond au motif de l'expression.

``````js hl_lines="3"
function estCourriel(valeur) {
    const regex_email = /^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/;
    return regex_email.test(valeur);
}

// Vrai
console.log(estCourriel("frechette.mathieu@cegepvicto.ca"));
// Faux
console.log(estCourriel("adresse-invalide"));


if(estCourriel("adresse-invalide")){
    console.log("Le courriel est invalide")
}
``````

Pour vous aider avec les regex : [https://regexr.com/](https://regexr.com/)

