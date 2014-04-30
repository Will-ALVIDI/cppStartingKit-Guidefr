C++ Starting Kit pour Sublime Text : Le Guide
==============================================

Ce guide est conçu pour les gens qui débutent le C++ et qui veulent utiliser un EDI léger comme Sublime Text l'est. Si vous suivez les instructions pas à pas vous aller obtenir des informations cruciales sur l'environnement de Sublime Text, le [**C++ Starting Kit**](https://github.com/kodLite/cppStartingKit) et un véritable point de départ pour vos projets en C++.

Si vous avez un tout autre profil vous trouverez surement des informations utiles pour personnaliser votre environnement Sublime Text C++ ou autre.

Ce guide couvre les points clefs pour démarrer l'utilisation de Sublime Text 3 pour C++ sous Windows 7 x64. Les étapes sont quasiment les même selon votre version de Sublime Text ou votre système d'exploitation.

J'ai çréé ce projet car en tant que débutant en programmation je pense qu'il est plus facile d'avoir toutes la documentation centralisées et uniformisées.

J'espère sincèrement que vous trouverez ici des informations pertinentes.

# Installation de Python

### Pourquoi Python est nécessaire

Sublime Text 2 est basé sur [Python 2.6](https://www.python.org/downloads/)(aussi compatible avec les versions supérieure jusqu'à la version 3) et Sublime Text 3 sur [Python 3](https://www.python.org/downloads/)(ou supérieur).

Par défaut Python n'est pas installé sur les systèmes Windows et si vous voulez tirer le meilleur parti de Sublime Text, notamment les plugins empaquetés qui sont le coeur de cette application, vous devez avoir la bonne version de Python installé. 

Pour le rendre fonctionnel vous devez :

* [Télécharger](https://www.python.org/downloads/) la version de Python appropriée à votre version de Sublime Text.

Vous pouvez avoir plusieurs versions de Python installé.

* Ajouter Python aux chemins de votre système.

Lisez entièrement la section [ajouter un dossier aux chemins système]() qui couvre comment le faire avec MinGW-w64 et adaptez-le pour l'installation de Python.

Le chemin que vous aurez à ajouter à la fin de la manipulation est le dossier principal de Python, là ou réside le ficher `python.exe`.

* Ensuite déconnectez-vous ou redémarrez votre ordinateur pour rendre effectif vos changements.

# Installer C++ Starting Kit

## Manuellement

(A rédiger)

### A partir de Package Control

(A faire)

# Utiliser C++ Starting Kit build system

## Prérequis

Si vous voulez utliser le [**C++ Starting Kit build system**](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build), qui est en fait le fichier [`CCpp.sublime-build`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build) dans le paquet de [**C++ Starting Kit**](https://github.com/kodLite/cppStartingKit), pour compiler vos programmes dans Sublime Text vous devez combiner 5 éléments :
* Installer un compilateur compatible g++. Dans notre cas MinGW-w64 pour des développements x86 et x64.
* [Ajouter votre compilateur à vos chemins système]().
* Redémarrer votre ordinateur.
* [Comprendre comment fonctionne le build system]().
* [Savoir comment utiliser le build system]().

### Installer MinGW-w64
* Allez sur la page d'accueil de MinGW-w64 à l'adresse [http://mingw-w64.sourceforge.net/](http://mingw-w64.sourceforge.net/). 

Ceci devrait vous donner la page ci-dessous ensuite cliquez sur la page de téléchargement entourée sur l'image suivante.

![MinGW-w64 project main page](https://github.com/kodLite/cppStartingKit-Guide/blob/master/screenshot/cppStartingKit/mingw-main-page-marked.jpg?raw=true)

* Pour simplifier les choses, sur la page de téléchargement, récupérez **l'installeur**, entouré sur l'image suivante. Il devrait vous donner un fichier nommé `mingw-builds-install.exe`.

![MinGW-w64 project download page](https://github.com/kodLite/cppStartingKit-Guide/blob/master/screenshot/cppStartingKit/mingw-download-page-marked.jpg?raw=true)

* Ensuite lancez `mingw-builds-install.exe`. Un processus d'installation va alors commencer où vous aurez deux choses auxquels faire attention,

La première est de choisir les options correctes pour cette installation. Changez l'architecture par défaut pour le x64 et gardez le reste comme tel. Ensuite cliquez sur le bouton `Next`.

![MinGW-w64 project options](https://github.com/kodLite/cppStartingKit-Guide/blob/master/screenshot/cppStartingKit/mingw-install-options-marked.jpg?raw=true)

Pour la prochaine séquence d'installation vous devez spécifier un chemin pour votre installation et garder en tête que vous en aurez besoin plus tard. Je vous recommande de l'installer dans un emplacement plus pratique comme `C:\MinGW\x64` car vous aurez surement plus tard besoin d'installer une autre version de MinGW et vous pourrez le faire proprement en ajoutant un nouveau dossier comme `C:\MinGW\x86` par exemple.

* Ensuite cliquez sur le bouton `Next` et laissez le processus d'installation se terminer.
* Maintenant vous devez [ajouter MinGW-w64 à vos chemins système]().

### Ajouter un dossier à vos chemins système

**Comme cette partie est utile à l'installation de Python, vous pouvez [cliquer ici]() pour retourner à la section Python.**

Ajouter un dossier à vos chemins système permet à votre système de partager des programmes qui peuvent être appelé par d'autre programmes.

La commande `g++`, qui est en réalité le fichier `g++.exe` situé dans votre dossier `MinGW-w64/bin`, est requise par le [**C++ Starting Kit build system**](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build) et dois être disponible dans vos chemins système pour permettre à Sublime Text d'y accéder. Pour ce faire suivez les étapes suivantes :

* Aller dans le menu `Démarrer`.
* Click droit sur `Ordinateur` et choisissez `Propriétés`.
* Sur le côté gauche choisissez `Paramètre système avancées`
* Allez sur l'onglet `Avancé` ensuite cliquez sur `Variables d'environnement`
* Dans `Variables Système` faite défiler jusqu'à trouver `path`, selectionnez-le.
* ENsuite cliquez sur le bouton `Modifier...`

Ceci va vous donner une liste de dossiers vitaux pour votre système. Soyez vraiment vigilant avec le contenu à l'intérieur de ce champs. Je vous recommande de le copier-coller(`Ctrl + A`, pour tout sélectionner, `Ctrl + C`, pour copier ce que vous aurez sélectionné, ensuite `Ctrl + V`, pour coller ce qui aura été copié) dans un nouveau document dans un emplacement fiable, comme ça vous pourrez ramener le tout à son état d'origine si nécessaire. 

Si vous suivez ce guide depuis le début vous devez ajouter à la fin de vos chemins système, à l'intérieur du champs, un point virgule `;` directement suivi par `C:/MinGW/x64/mingw64/bin`. 

* Ensuite déconnectez vous ou redémarrez votre ordinateur pour rendre effectif les changements.

## Comprendre le C++ Starting Kit build system

**Introduction**

Les build systems dans Sublime Text sont dépendants des projets. Il est difficile d'en concocter un qui soit efficace pour tous les types de projet que vous rencontrerez. Le [**C++ Starting Kit build system**](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build) et la documentation qui va suivre sont une introduction et un point de départ pour vos futurs Sublime build systems.

Je vous recommande de créer votre premier build system dans le dossier `/User` de Sublime Text :

* Allez dans le dossier `Sublime Text/Data/Packages/User`.
* Ou à partir de Sublime Text en allant dans le menu `Preferences > Browse Packages...` ensuite allez dans le dossier `/User`.
* Créer un fichier avec nom facilement reconnaissable comme `User - C++.sublime-build`.
* Copier-coller ce qui suit. C'est une copy du contenu de [**C++ Starting Kit build system**](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build) :

		{
			"cmd": ["g++", "-Wall","*.cpp", "-I", "../header","-o", "${file_path}/${file_base_name}"],
			"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
			"working_dir": "${file_path}",
			"selector": "source.c++",
			"shell" : true,
		
			"variants":
			[
				{
					"cmd": ["start","cmd", "/k","${file_path}/${file_base_name}"],
					"name": "Run"
				},
			]
		}

* Sauvegardez les changements.
* Ensuite activez le build system personnalisé en allant dans le menu `Tools > Build System` et choisissez votre nouveau build system intitulé `User - C++`.

La premiére partie de ce build system qui commence par `"cmd"` représente la fonction `Build`. La seconde, depuis `"variants"`, définie la fonction `Run`.

Comme les processus de compilation pourrais à eux seule couvrir un guide entier je vais juste détailler la première ligne qui est la plus importante et vous rediriger vers la [documentation officielle de MinGW-w64](http://www.mingw.org/wiki) et la [documentation Non-officielle de Sublime Text](http://sublime-text-unofficial-documentation.readthedocs.org/en/latest/reference/build_systems.html) pour améliorer vos connaissances :

* `"g++"` appelle le lancement de `g++.exe`, le compilateur.
* `"-Wall"`, de l'anglais "warn all"(alerter de tout), vous alertera pour toute erreur de compilation.
* `"*.cpp"` va inclure tous les fichers `*.cpp` contenu dans votre dossier.
* `"-I"`, pour "include"(inclure), et `"../header"` vont inclure un dossier nommé "header", un niveau au dessus du répertoire du courant fichier.
* `"-o"`, for "output"(sortie), suivi de `"${file_path}/${file_base_name}"` va sortir un exécutable, un ficher `*.exe`, à l'intérieur du chemin du ficher courant avec comme nom la base du nom de votre ficher.

**Meilleur pratique : tester vos build systems avec l'invite de commande.**

Les commandes dans le [**C++ Starting Kit build system**](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build) sont reproductibles et testables dans l'invite de commande Windows. Testez vos build systems Sublime Text de cette maniére avant de les adapter à vos build systems personnalisés.

Quelques étapes sont nécessaire pour le faire :
* Localisez le dossier qui contient votre programme principal.
* Appuyez sur `Shift + Click Droit` ensuite choisissez `Ouvrir l'invite de commande ici`(<<<<<==== A vérifier). Ceci va ouvrir une invite de commande prête à travailler dans votre dossier de projet et vous évite la même manipulation entièrement en lignes de commands.
* Ensuite essayez de suivre les commandes qui suivent qui sont l'eéquivalent du [**C++ Starting Kit build system**](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build) :

	**`g++ -Wall *.cpp -I ../header -o monProgramme.exe`**

Si vous lancé un build de votre programme avec ces commandes vous aurez comme résultat un ficher `monProgramme.exe` dans votre dossier qui peut être lancé en tapant son nom dans l'invite de commande suivi de `Entrée` ou en double cliquant sur le dit fichier dans votre dossier de travail.

### Utiliser le C++ Starting Kit build system

Les commandes par défaut pour `Build` et `Run` avec [**C++ Starting Kit build system**](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build) sont :
* `Ctrl + B` pour lancer un build de votre programme.
* `Ctrl + Shit + B` pour lancer votre program.

# Personnaliser votre jeu de couleurs(color scheme)

Si vous utilisez un jeu de couleurs par défaut ou téléchargé sur Internet vous devez allez devoir ajouter [la scope list de **C++ Starting Kit**]() dans votre fichier de configuration `*.tmTheme`.

Une alternative recommandée est d'essayé le [Oasis Theme](https://github.com/kodLite/Oasis-Theme) spéciallement conçu pour.
 
Sinon vous pouvez jeter un oeil à ce qui suit. La partie suivante est conçue comme un enselbe d'astuces utiles pour personnaliser votre environnement Sublime Text.

### Localiser le fichier de configuration de votre jeu de couleurs

* Les jeux de couleurs par défaut sont installés dans le dossier `Sublime Text/Packages` dans un fichier appelé `Color Scheme - Default.sublime-package`. (voir [comment éditer un paquet *.sublime-package]())
* Les jeux de couleurs dit User(utlisateur) sont dans le dossier `Sublime Text/Data/Packages/User` en tant que fichier `*.tmTheme`.

Si vous voulez personnaliser un jeu de couleurs par défaut je vous recommande de le copier et de le renommer dans votre dossier `Sublime Text/Data/Packages/User`.

### Changer votre jeu de couleurs

* Allez dans le menu `Preferences > Color Scheme` et faites votre choix entre les jeux de couleurs `Color Scheme - Default` et `User` si vous en avez.

### Trouver le nom d'un scope(<<<<<<<====== trouver le nom en français)

* Mettez votre curseur sous le scope dont vous voulez connaitre le nom.
* Tapez `Ctrl + Alt + Shift + P`.
* Le nom va apparaître en bas de votre interface Sublime Text.

### Chercher un scope dans votre ficher de configuration de jeu de couleurs

* Faites un recherche en tapant `Ctrl + F`.
* Entrez ce que vous souhaitez chercher dans le champ en bas et n'oubliez pas de vous servir des commandes `Find`(Trouver) and `Find Prev`(Trouver avant).

### Ajouter un scope manquant dans otre ficher de configuration de jeu de couleurs

Si vous êtes sur qu'il vous manque un scope dans votre fichier `*.tmTheme`, qui contient votre jeu de couleurs, ajoutez les lignes suivantes et remplissez correctement les champs entre les tags(`<tag>Votre spécification</tag>`)

If you are sure that a scope is missing in your `*.tmTheme` file, which contain your color scheme, add the following lines and fill corretly the fields between the tags(`<tag>Your specification</tag>`) :

		<dict>
			<key>name</key>
			<string>Scope name</string> 		<!-- Enter a name for your scope here. -->
			<key>scope</key>
			<string>Scope definition</string> 	<!-- Enter your scopes here. (ex : keyword.ccpp) -->
			<key>settings</key>
			<dict>
				<key>fontStyle</key>
				<string></string> 				<!-- Choose a style (ex : italic, bold, italic bold) -->
				<key>foreground</key>
				<string></string> 				<!-- Choose a color (ex : #49a629) -->
			</dict>
		</dict>

### La scope liste de **C++ Starting Kit

**Arithmetic operators**(keyword.operator.arithmetic.ccpp), **Brackets**(open.curly.bracket.ccpp, close.curly.bracket.ccpp,open.round.bracket.ccpp, close.round.bracket.ccpp, open.angle.bracket.ccpp, close.angle.bracket.ccpp, open.curly.bracket.ovr.ccpp, close.curly.bracket.ovr.ccpp), **Block brackets**(open.curly.bracket.block.ccpp, close.curly.bracket.block.ccpp), **Punctuation**(period.ccpp, coma.ccpp,semi_colon.ccpp), **End of line semi colon**(semi_colon.eol.ccpp), **Function support**(function.support.ccpp)

# Personnalisez votre définition syntaxique

## Ce que vous devez savoir

### Introduction

`*.sublime-package` dans votre dossier `Sublime Text/Packages` contient les définitions spécifiques des languages par défaut tout comme les thèmes par défaut, `Theme - Default.sublime-package`, et les jeux de couleurs par défaut, `Color Scheme - Default.sublime-package`.

La définition syntaxique est principalement définie par un fichier de configuration, `*.tmLanguage`, dans ces `*.sublime-package`.

### Comment editer un *.sublime-package 

`*.sublime-package` comme [**C++ Starting Kit**](https://github.com/kodLite/cppStartingKit) sont des archives `*.zip`. Si vous voulez modifer les fichiers à l'intérieur vous devez suivre les étapes suivantes :
* dans votre dossier `Sublime Text/Packages` vous devez trouver le paquet que vous voulez modifier.
* Copiez et collez le dans un emplacement pratique et faites vos changements sur ce fichier.
* Pour ouvrir le paquet vous devez renommer le fichier en `*.zip` puis l'extraire.
* Dans le dossier extrait vous allez trouver les fichiers éditables.
* Quand vous avez fini, sauvegardez vos changements.
* Fermez Sublime Text.
* "Ré-archivez" votre dossier extrait avec l'extension "*.zip" ensuite renommez le en `*.sublime-package`.
* Copiez votre mise à jour `*.sublime-package` et écrasez celle dans votre dossier `Sublime Text/Packages`.
* Relancez Sublime Text.

### Structure globale de CCpp.tmLanguage

Le fichier [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage) est la définition syntaxique inclu dans le paquet[**C++ Starting Kit**](https://github.com/kodLite/cppStartingKit)

Il est basé sur le fichier par défaut `C++.sublime-package` et ajusté comme suit :

* `C.tmLanguage` et `C++.tmLanguage`, qui sont responsables de la définition syntaxique pour la prise en charge par défaut du C et C++, a été découpé, documenté, fusionné et amélioré en [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage).
* `C++.sublime-build`, qui contient le build system par défaut du C et C++, a été personnalisé et renommé [`CCpp.sublime-build`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build).
* `C++.sublime-settings`, qui spécifie les types de fichier pris en charge, a juste été renommé [`CCpp.sublime-settings`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-settings). 
* Tous les autres fichiers ont été préservés.

### Logique derrière CCpp.tmLanguage

Le fichier [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage) a été codé avec une logique trés simple : un comportement principal est établi ensuite de petit bout de code sont ajouté pour améliorer les fonctionnalités et éviter les comportements indésirables.

Par exemple les accolades(curly brackets) ont été definies en tant que `open.curly.bracket.ccpp` et `close.curly.bracket.ccpp`. Ensuite `open.curly.bracket.block.ccpp` et `close.curly.bracket.block.ccpp` ont été ajouté pour recouvrir cette premiére définition et définir ce que l'on pourrait appeler le "block detection"(détection de blocks). Après tests il semble que quelques exceptions appraissent et elles sont corrigés en ajoutant une couche de code supplémentaire.

![C++ Starting Kit logic](https://github.com/kodLite/cppStartingKit-Guide/blob/master/screenshot/cppStartingKit/logic-ccpp-illustrated.jpg?raw=true)

Si vous voulez suivre ce processus vous devez mettre vos comportements principaux en dessous, et pas le contraire. (voir l'exemple dessous)

![C++ Starting Kit Syntax Definition Override](https://github.com/kodLite/cppStartingKit-Guide/blob/master/screenshot/cppStartingKit/overrides.jpg?raw=true)

L'idée principale derrière cette approche est d'avoir une flexibilité et une aisance sur la maintenance du système sans pour autant avoir à tout casser. 

# Aller plus loin 

Sur cette dernière partie je vous partage mes ressources pour approfondir vos connaissances, elles sont principalement toutes en anglais.

### Gestion de projets sous Sublime Text

[Cette vidéo](http://www.youtube.com/watch?v=Kr5ztsD3Yr4) est un bon point de départ pour la maitrise de la gestion des projets sous Sublime Text.

### Plugins

La gestion de plugins est le coeur de Sublime Text je vous recommande chaudement de visiter régulièrement [Package Control - Le site officiel](https://sublime.wbond.net/) pour découvrir, tester et contribuer à faire avancer les projets de la communauté.

### Expressions régulières

Si vous souhaitez aller plus dans la définition syntaxique je vous recommande de vous attarder sur les expressions régulières. Voici trois ressources qui m'ont d'ailleurs été utiles pour [**C++ Starting Kit**](https://github.com/kodLite/cppStartingKit) :
* [Themeforest - Blog communautaire](http://blog.themeforest.net/screencasts/regular-expressions-for-dummies/)
* [RegExr par gSkinner](http://www.regexr.com/v1/)
* [Regular-expressions.info](http://www.regular-expressions.info/)


