## Tout code, peu importe les bases sur lesquelles il est établi, devrait ressembler au code tapé par une seule personne, peu importe le nombre de personnes ayant contribué.

> "Il est essentiel de réaliser que pour la réussite d'un projet, un bon intervenant ne doit pas coder pour soi-même mais pour les autres. Si un millier de personnes doivent utiliser votre code, écrivez-le avec un maximum de clarté, non pour des préférences personnelles, mais pour être au plus près du besoin." - Idan Gazit

### Processus de "build" et de déploiement
Toujours tenter d'inclure des moyens de vérifier le code implémenté avec Lint, tester et minifier les fichiers afin d'avoir de meilleures performances en production.

### Testabilité
Les projets doivent inclure certaines formes de test unitaire : tests d'implémentation et de périmètre fonctionnel.

### Syntaxe / Style
##### Encodage fichier
Utiliser l'encodage de texte Unicode (**UTF-8**)

##### Fin de ligne
Utiliser les fins de ligne Unix (LF)

1. #### Indentation
Indenter avec 2 espaces. Pas de tabulation

* Pour la lisibilité, paramétrez votre éditeur avec une indentation de deux caractères — ce qui veut dire deux espaces ou une tabulation représentant deux espaces.
* Travaillez toujours avec le mode "afficher les caractères invisibles" actif. Les avantages de cette pratique sont :
 * Améliorer la cohérence du code.
 * Éliminer les espaces de fin de ligne. Activer la suppression automatique si votre éditeur de code le permet. 
 * Éliminer les espaces utilisées pour des lignes blanches.
 * Améliorer la lisibilité de vos "commit" et des "diff".

#### 1. Longueur de ligne
Chaque ligne de texte dans le code doit faire au maximum **80 caractères** de long.

Vérifiez que votre éditeur de code affiche un guide de page sur 80 caractères

Exceptions :

#### 2. Syntaxe
A. Parenthèses, Accolades, Sauts de ligne

	//if/else/for/while/try ont toujours des espaces, des parenthèses et plusieurs sauts de ligne cela améliore la lisibilité

	//Exemples de mauvaises pratiques

	if(condition) doSomething();

	while(condition) iterating++;

	for(var i=0;i<100;i++) someIterativeFn();

	//Bonnes pratiques, utilisez les espaces afin d'améliorer la lisibilité

	if ( condition ) {
		// déclarations
	}

	while ( condition ) {
		// déclarations
	}

	for ( var i = 0; i < 100; i++ ) {
		// déclarations
	}

	// même mieux :
	var i,
	length = 100;

	for ( i = 0; i < length; i++ ) {
		// déclarations
	}

	// Ou...
	var i = 0,
		length = 100;

	for ( ; i < length; i++ ) {
		// déclarations
	}

	var prop;
	for ( prop in object ) {
		// déclarations
	}

	if ( true ) {
		// déclarations
	} else {
		// déclarations
	}



B. Variables

En général, utilisez functionNamesLikeThis, variableNamesLikeThis, ClassNamesLikeThis, EnumNamesLikeThis, methodNamesLikeThis, CONSTANT_VALUES_LIKE_THIS, foo.namespaceNamesLikeThis.bar, et filenameslikethis.js.

B. Déclaration, Affectation, Fonction ( Nommage, Expression, Constructeur )

	//Variables
	var foo = "bar",
	num = 1,
	undef;

	// Notations littérales :
	var array = [],
	object = {};

	//Utiliser une unique déclaration `var` par portée de (fonction) améliore la
	lisibilité et permet de garder une déclaration séparée du
	corps de la fonction
	(en adéquation avec la portée des variables JS).

	//Mauvais exemple
	var foo = "";
	var bar = "";
	var qux;

	//Bonne pratique

	var foo = "",
	bar = "",
	quux;

	//La déclaration des variables 'var' doit toujours être au début
	//de la portée de chaque fonction.

	Mauvaise pratique
	function foo() {

		// déclarations
		var bar = "",
			qux;
	}

	//Bonne pratique
	function foo() {
		var bar = "",
		qux;

		// toutes les autres déclarations sont après la déclaration des variables.
	}

	// Déclaration de fonction nommée
	function foo( arg1, argN ) {

	}

	// Utilisation
	foo( arg1, argN );


	// Déclaration de fonction nommée
	function square( number ) {
		return number * number;
	}

	// Utilisation
	square( 10 );

	// Passage d'une callback par variable nommée
	function square( number, callback ) {
		callback( number * number );
	}

	square( 10, function( square ) {
		// déclaration de la callback
	});


	// Expression de fonction
	var square = function( number ) {
		// Renvoie quelque chose de pertinent
		return number * number;
	};

	// Expression de fonction avec un identifiant
	// Cette forme préférée a pour valeur ajoutée d'être en mesure de se faire appeler
	// et d'avoir une identité dans les traces de pile
	var factorial = function factorial( number ) {
		if ( number < 2 ) {
			return 1;
		}

		return number * factorial( number-1 );
	};


	// Déclaration de Constructeur
	function FooBar( options ) {

		this.options = options;
	}

	// Utilisation
	var fooBar = new FooBar({ a: "alpha" });

	fooBar.options;
	// { a: "alpha" }

#### Formattage du code


### Règle du Langage