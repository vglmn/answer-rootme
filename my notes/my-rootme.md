# Solution exercices rootme :
## Web client :

HTML : https://www.root-me.org/fr/Challenges/Web-Client/HTML-boutons-desactives dans l'inspection d'élément on peut voir que les input sont disabled `<input disabled="" type="text" name="auth-login" value="">`, il suffit d'effacer le "disabled". (https://developer.mozilla.org/fr/docs/Web/HTML/Attributes/disabled)

JS Auth : https://www.root-me.org/fr/Challenges/Web-Client/Javascript-Authentification dans l'inspection d'élément, la balise head contient une balise `<script type="text/javascript" src="login.js"></script>`, le login.js contient les informations.

JS Auth 2 : https://www.root-me.org/fr/Challenges/Web-Client/Javascript-Authentification-2 même principe que JS Auth, seulement dans le fichier .js on peut voir la variable contenant les accès.

JS Source : https://www.root-me.org/fr/Challenges/Web-Client/Javascript-Source même principe que JS Auth, seulement le script est directement mis entre balise script

JS Obfuscation : https://www.root-me.org/fr/Challenges/Web-Client/Javascript-Obfuscation-1 le pass est définis, le script nous dis `if h == unescape(pass))`, il suffit donc d'aller en console, entrer `pass = '%63%70%61%73%62%69%65%6e%64%75%72%70%61%73%73%77%6f%72%64';` suivis de `unescape(pass)`.

JS Obfuscation 2 : https://www.root-me.org/fr/Challenges/Web-Client/Javascript-Obfuscation-2 la variable pass est définis comme `var pass = unescape("unescape%28%22String.fromCharCode%2528104%252C68%252C117%252C102%252C106%252C100%252C107%252C105%252C49%252C53%252C54%2529%22%29");`, il faut donc `unescape(pass)`, puis faire un `unescape` en enlevant les guillements de la string, ce qui permet d'avoir le mot de passe.

JS Native Code : https://www.root-me.org/fr/Challenges/Web-Client/Javascript-Native-code On peut voir qu'en copiant le code dans la console on a une pop-up nous demandant le mot de passe, en rentrant le code sur https://www.dcode.fr/desobfuscateur-javascript le résultat a été donné. Une autre solution aurait été d'ajouté `toString()` à la fin du code en remplaçant les deux dernières parenthèses.

## Obfuscation

Aussi appelé assombrissement, obscurcissement ou brouillage, est une stratégie de gestion de l'information qui vise à obscurcir le sens qui peut être tiré d'un message. Cette stratégie peut être intentionnelle ou involontaire (https://fr.wikipedia.org/wiki/Offuscation )

Ce qui a généré le code dans l'exercice JS Obfuscation est escape() : "La fonction escape() permet de renvoyer une nouvelle chaîne de caractères dont certains caractères ont été remplacés par leur séquence d'échappement hexadécimale" (https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/escape ) la phrase ayant été de l'héxadécimale il suffit de la passer au unescape (https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/unescape ) qui calcule une nouvelle chaîne de caractères et remplace les séquences d'échappement hexadécimales par les caractères qu'elles représentent.