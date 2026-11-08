# Structure d'un formulaire
Les formulaires HTML sont utilisés pour échanger de l'informations entre les usagers et le site web qu'ils visitent. Ils sont composés de plusieurs éléments html (input, select) qui permettent à l'utilisateur de saisir l'information à envoyer. Elle sera ensuite transmise vers un serveur web où elle sera traitée.

## L'élément form
Élément essentiel à tout formulaire, la balise form est en quelque sorte le conteneur de notre formulaire. Tous ce qui si retrouve sera traité comme faisant partie du formulaire. Elle a deux attributs spécifiques qui dictent la façon dont le formulaire va envoyer l'information au serveur : **action** et **method**.

**Exemple**

``````html
<form id="formulaire_contact" method="post" action="/traitement.php">
	<!-- Contenu de mon formulaire -->
</form>
``````

### action
L'attribut action prend comme valeur une URL vers laquelle les données seront acheminées. On peut aussi donner un chemin relatif vers un fichier qui traitera les données du formulaire sur le serveur.

### method
L'attribut method défini de quelle façon les données seront acheminées. Les valeurs possibles sont GET ou POST. 

#### GET
Les données sont incluses dans l'URL défini par l'attribut action. L'URL se termine par un symbole ? suivi d'une série de paire "nom/valeur" pour chaque contrôle, le tout séparé par le symbole &. Attention, les informations envoyées au serveur sont lisibles directement dans l'url de la requête. Cette méthode n'est donc pas très sécuritaire au niveau de la protection des données et devraient être utilisé dans certain cas précis, comme par exemple une recherche de produits dans un magasin en ligne. 

Voici un exemple de requête d'une recherche Google où on peut très bien le voir : `https://www.google.com/search?client=firefox-b-d&q=photo+de+petits+chats`. La requête est envoyé à l'adresse www.google.com/search avec les informations suivantes : 

| clé    | valeur                | description    |
| ------ | --------------------- | -------------- |
| client | firefox-b-d           | Mon navigateur |
| q      | photo+de+petits+chats | Ma recherche   |


#### POST

Dans une requête post les données sont incluses dans le corps de la requête. Les données ne sont pas explicitement vu par l'usager et ça nous permet d'envoyer une plus grande quantité d'informations. ==C'est cette méthode que nous allons privilégiée==.