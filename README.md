Démarrer un projet ionic 3
--------------------

Prérequis
==

Un minimum :

    * Connaissances NPM
    * Connaissances TypeScript, HTML5, CSS3
    * Connaissances Angular 4, ou minimum Angular 2
    * Connaissances Cordova
    * Disposer des SDK pour la/les platform(s) où déployer

Le top :

    * Connaissances sur la/les platform(s) cible(s)
    * Connaissances JavaScript (es6)
    * Un environnement Linux ou Mac pour la ligne de commande ... :)
    * Et pourquoi pas des connaissances de batch

Installation de l'environnement
-

code

    npm install -g ionic cordova 

C'est tout, l'environnement est près !

Lancement du projet
==

code

    ionic start project-name [template-name]

Ionic va installer tous les pacquets nécessaires pour lancer le projet avant même de commencer les développements

Builder et lancer le projet
-

code

    ionic cordova add platform android
    ionic cordova build android
    ionic cordova run android

Le cli Ionic
==

Dans ce type de projet, certaines manipulations peuvent être redondantes et lourdes. Pour cela, nous disposons
d'un cli qui va permettre d'automatiser des tâches (add platform, build, run), de générer des fichiers, ou encore
de récupérer des dépendences.

Certaines des commandes disposent de shortcut afin d'accélérer notre frappe.

Débugger en live
-

Une commande très utilisée dans le cli pour développer permet de transpiler le typescript et de le déployer
sur votre navigateur par défaut. Cette commande est serve.
Sans option, cette commande va être exécuté avec le livereload, c'est-à-dire que dès qu'une modification d'un de 
nos fichiers de sources sera détectée, une nouvelle transpilation va s'exécuter suivi d'un rafraichissement de votre
page web ouverte dans votre navigateur.

code

    ionic serve

Générer une page
-

Voyons maintenant comment utiliser ce cli pour créer notre nouvelle page

code

    ionic generate|g page page-name

Le dossier généré contient un fichier .module.ts afin de regrouper éventuellement de plus petits bloques spécifiques à cette page.
Ce fichier sera utile si la page dépend de nombreuses logiques utilisant, par exemple, des services, des pipes, d'autres composants
qui lui sont spécifiques. Il est conseillé de mettre ces fichiers dans un dossier shared s'ils sont transverses à l'application.
Dans notre cas, nous pouvons le supprimer.
En revanche, lorsqu'il est utilisé, il devra ensuite être importé et déclaré dans la propriété imports de notre module principal.
Dans la mesure où la page n'a pas besoin de ce module.ts, elle devra être déclaré dans la propriété "declarations" si elle est utilisée
seulement en temps que composant et dans la propriété "entryComponents" pour naviguer.

Développer
-

### Menu

Ionic apporte une solution pour afficher diverses menus à l'image d'un device. Ces menus sont gérés dans le fichier
src/app/app.component.ts avec un tableau de pages contenant un titre et un composant.

### Navigation entre les pages

Le service NavController va permettre de naviguer d'une page à une autre suivant une pile. Cette pile va permettre de garder
un historique de navigation. En effet, lors d'un appel à navCtrl.push(ComposantPage), la page va s'ouvrir. Lors d'un
appel à navCtrl.pop(), la page courrante va se fermer pour donner place à la précédente.