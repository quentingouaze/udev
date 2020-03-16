# Setup pour bosser sur vos pc perso pour les cours à distance

## 1-> [Ajout d'un élément au "PATH" (Variables d'environnement système)](https://github.com/quentingouaze/udev/blob/master/install.md#ajout-dun-%C3%A9l%C3%A9ment-au-path-variables-denvironnement-syst%C3%A8me)
## 2-> [Gestionnaire de paquets "Chocolatey"](https://github.com/quentingouaze/udev/blob/master/install.md#gestionnaire-de-paquets-chocolatey)

## 3-> [PHP/Mysql](https://github.com/quentingouaze/udev/blob/master/install.md#phpmysql) 
### 3a-> [Pour lancer un serveur PHP indépendant de wamp](https://github.com/quentingouaze/udev/blob/master/install.md#pour-lancer-un-serveur-php-ind%C3%A9pendant-de-wamp-dans-nimporte-quel-dossier)
## 4-> [Frameworks PHP (Symfony, Laravel..)](https://github.com/quentingouaze/udev/blob/master/install.md#frameworks-php-symfony-laravel)
### 4a-> [Symfony](https://github.com/quentingouaze/udev/blob/master/install.md#symfony)
### 4b-> [Laravel ](https://github.com/quentingouaze/udev/blob/master/install.md#laravel)
## 5-> [Frameworks Javascript (React, Vue, Angular..)](https://github.com/quentingouaze/udev/blob/master/install.md#frameworks-javascript-react-vue-angular)
### 5a-> [React](https://github.com/quentingouaze/udev/blob/master/install.md#react)
### 5b-> [VueJS](https://github.com/quentingouaze/udev/blob/master/install.md#vuejs)
### 5c-> [Angular](https://github.com/quentingouaze/udev/blob/master/install.md#angular)
### 6-> [Java (+Maven)](https://github.com/quentingouaze/udev/blob/master/install.md#java)


## Ajout d'un élément au "PATH" (Variables d'environnement système)

Dans la barre de recherche Windows: "environnement" et vous devriez trouver "Modifier les variables d'environnement Systeme", qui ouvrira les "Propriétés système".
Ici, cliquer sur "Variables d'environnement", puis dans la liste de Variables système (en bas), sélectionner "PATH" et cliquer sur "Modifier".

Vous devrez trouver le chemin vers les éxécutables dont vous aurez besoin, par exemple pour PHP: C:\wamp64\bin\php\php7.4.0 ou pour Java C:\Program Files\Java\jdk1.8.0_211\bin

Une fois ajouté, vous pouvez vérifier si l'executable fonctionne en l'appelant via la ligne de commande windows, powershell ou le git bash, avec des commandes comme les suivantes:
```
php -v
java --version
javac --version
```
## Gestionnaire de paquets "Chocolatey"
En tant qu'administrateur (Powershell):
Vérifier si Get-ExecutionPolicy retourne "Restricted". Si c'est le cas, utiliser:
```
Set-ExecutionPolicy Bypass -Scope Process
```
Puis lancer la commande suivante:
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
Ici, lancez une nouvelle invite de commande pour vérifier si tout fonctionne:
```choco```
Cette commande devrait vous afficher un numero de version
Vous pouvez ensuite installer des paquets (par exemple, tree) via la commande install:
```
choco install tree
```
## PHP/Mysql

Télécharger WampServer sur leur site officiel: http://www.wampserver.com/fr/ 
(sélectionner la version 64Bits ou 32 Bits en fonction de votre machine)
Vous devez avoir installé Visual Studio 2012 VC 11 vcredist_x64/86.exe disponible ici : http://www.microsoft.com/en-us/download/details.aspx?id=30679

### Pour lancer un serveur PHP indépendant de wamp, dans n'importe quel dossier:

cd dans le dossier en question dans la ligne de commande ou le git bash, puis:
``` php -S localhost:#### ```
où "####" est un numéro de port au choix, qui doit être différents de ceux déjà utilisés par wamp, npm ou autre, et qui vous permettra d'ouvrir votre projet dans un navigateur

## Frameworks PHP (Symfony, Laravel..)
Vous aurez besoin du gestionnaire de dépendances pour PHP "Composer" disponible ici: https://getcomposer.org/download/ 
C'est un simple .exe à lancer sous windows, et quelques commandes sous linux/mac
### Symfony
Là aussi, un simple .exe à lancer, dispo ici: https://symfony.com/download
Vous pourrez ensuite créer un nouveau projet via 
```
symfony new --full my-project
```
ou via composer:
```
composer create-project symfony/website-skeleton my_project
```
### Laravel 
Une commande composer suffit pour installer laravel/installer globalement:
```
composer global require laravel/installer
```
Ensuite, pour créer un nouveau projet:
```
laravel new my_project
```

## Frameworks Javascript (React, Vue, Angular..)
Vous aurez besoin de NodeJS, qui inclut le gestionnaire de paquet Node Package Manager (NPM), récupérable ici: https://nodejs.org/en/ (sélectionnez la version LTS, et pas Current, pour moins de prise de tête)
### React
Le packet pour facilier l'installation de React est "create-react-app", installable via npm:
```
npm install -g create-react-app
```
Puis pour créer un projet:
```
npm create-react-app my_project
```
### VueJS
La CLI de vue est installable via NPM:
``` 
npm install -g @vue/cli
```
Pour créer un projet:
```
vue create my_project
```
Pour lancer le projet, se placer dans le dossier via "cd" puis:
```npm run start```
### Angular
Là aussi, l'installation globale se fait via NPM:
```
npm install -g @angular/cli
```
Pour créer un projet:
```
ng new my_project
```
Pour lancer le projet, se déplacer dans le dossier via "cd" puis
```
ng serve
```

## Java
Télécharger l'[executable](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html) pour installer Java Development Kit 8 et l'executer.
Télécharger l'[executable](https://maven.apache.org/download.cgi) d'installation de Maven et l'éxecuter.
Ajouter les dossiers de Java et de Maven au PATH [(Variables d'environnement Systeme)](https://github.com/quentingouaze/udev/blob/master/install.md#ajout-dun-%C3%A9l%C3%A9ment-au-path-variables-denvironnement-syst%C3%A8me)
Vérifier la bonne installation des logiciels (dans une nouvelle fenêtre de git bash ou de la CLI windows, ou après avoir rechargé votre fichier source)
```
java -version

javac -version

mvn -v
```
Assurer l'encodage en UTF-8 pour éviter des bugs de caractères/symboles:
```
echo "alias java='java -Dfile.encoding=UTF-8'" >> ~/.bash_profile
echo "alias javac='javac -encoding utf8'" >> ~/.bash_profile
```
Vérifier si les commandes précédentes ont fonctionné:
```
java -XshowSettings 2>&1 | grep encoding
```
qui devrait vous donner: 
```
 file.encoding = UTF-8
    file.encoding.pkg = sun.io
    sun.io.unicode.encoding = UnicodeLittle
    sun.jnu.encoding = Cp1252
```
