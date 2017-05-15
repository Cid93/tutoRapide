Démarrer un projet ionic 3
--------------------

Prérequis
==

Un minimum :

    * Connaissances NPM
    * Connaissances TypeScript, HTML5, CSS3
    * Connaissances Angular 4, ou minimum Angular 2
    * Connaissances Cordova

Le top :

    * Connaissances sur la/les platform(s) sur lesquelles vous voulez déployer
    * Connaissances JavaScript (es6)
    * Un environnement Linux ou Mac pour la ligne de commande ... :)

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
