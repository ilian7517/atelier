# 📒 Mon carnet de bord

**Nom :Ulloa** 

**Prénom :Ilian** 

**Adresse de mon site :** [https://ilian7517.pythonanywhere.com]

> Modifiez ce fichier directement sur GitHub (icône crayon ✏️) pour répondre aux questions de chaque exercice.
> Écrivez avec vos propres mots : une réponse courte et juste vaut mieux qu'un long copier-coller ! 🙂

---

## 🟢 Exercice 1 — Mon premier déploiement

1. Où se trouve physiquement le code qui fabrique votre page : sur votre ordinateur, sur GitHub ou sur PythonAnywhere ?

   > _Ma réponse :_  Le code qui fabrique ma page se trouve sur pythonanywhere car c'est le serveur qui l'exécute Git sert seulement a stocker

2. Pourquoi votre voisin(e) peut-il voir votre site, alors que vous n'avez rien installé sur son ordinateur ?

   > _Ma réponse :_  parce que le site fonctionne sur le serveur de pythonanywhere

---

## 🟢 Exercice 2 — Les URL et les routes

1. Dans l'URL `https://www.google.com/maps`, quel est le nom de domaine ? Quel est le chemin ?

   > _Ma réponse :_ > Le nom de domaine est www.google.com c'est l'adresse du serveur. Le chemin est /maps c'est la page demandée sur ce serveur.

2. Que veut dire le message *Not Found* ? Qui l'a envoyé : votre navigateur ou le serveur ?

   > _Ma réponse :_ Not Found (erreur 404) veut dire que le serveur n'a trouvé aucune page correspondant à l'adresse demandée. C'est le serveur qui l'envoie pas mon navigateur.

3. Que se passe-t-il si deux fonctions portent le même nom dans `flask_app.py` ? (Indice : essayez, puis lisez l'Error log.)

   > _Ma réponse :_ Si deux fonctions portent le même nom Flask plante au démarrage et le site affiche "Something went wrong". Dans l'Error log on voit une AssertionError : View function mapping is overwriting an existing endpoint function.

---

## 🔵 Exercice 3 — Le langage HTML

1. Quelle est la différence entre ce que le serveur **envoie** et ce que le navigateur **affiche** ?

   > _Ma réponse :_  Le serveur envoie seulement du texte, avec des balises HTML. Le navigateur lit ces balises et les transforme en page mise en forme (titres, listes, images). On voit le texte brut avec Ctrl + U.

2. À quoi servent les balises `<h1>`, `<p>`, `<ul>` et `<li>` ?

   > _Ma réponse :_  <h1> sert à faire un titre principal, <p> un paragraphe, <ul> une liste à puces et <li> un élément de cette liste.

3. Pourquoi l'image s'affiche-t-elle alors qu'elle n'est pas sur votre serveur ?

   > _Ma réponse :_ L'image s'affiche parce que la balise <img> contient l'adresse (URL) de l'image. Le navigateur envoie une requête à ce serveur (Wikimedia) pour la télécharger, puis l'affiche dans la page.

---

## 🔵 Exercice 4 — Les templates

1. Pourquoi est-ce une bonne idée de séparer le code Python et le HTML ? (Pensez à une équipe avec un développeur et un graphiste.)

   > _Ma réponse :_ Séparer le code Python et le HTML permet à chacun de travailler sur sa partie : le développeur sur la logique (flask_app.py), le graphiste sur l'apparence (les templates), sans se gêner ni risquer de casser le travail de l'autre. Le code reste aussi plus lisible.

2. Les `{{ prenom }}` sont-ils remplacés par le serveur ou par le navigateur ? Comment l'avez-vous vérifié ?

   > _Ma réponse :_  Les {{ prenom }} sont remplacés par le serveur, avant l'envoi de la page. Je l'ai vérifié avec Ctrl + U : le code source ne contient plus les {{ }}, seulement les vraies valeurs.

---

## 🔵 Exercice 5 — Le CSS et les liens

1. Quelle est la différence de rôle entre le HTML et le CSS ?

   > _Ma réponse :_ Le HTML décrit la structure de la page (titre, paragraphe, liste, lien). Le CSS décrit son apparence (couleurs, police, marges).

2. Pour afficher votre page `/presentation`, combien de fichiers le navigateur doit-il télécharger ? (Vous pourrez le vérifier à l'exercice suivant !)

   > _Ma réponse :_ Le navigateur télécharge 3 fichiers : la page HTML, le fichier style.css, et l'image du logo Python qui vient de Wikimedia.

3. Pourquoi faut-il parfois faire **Ctrl + F5** pour voir les changements de CSS ?

   > _Ma réponse :_ Le navigateur garde en mémoire (cache) les fichiers déjà téléchargés, dont le CSS, pour aller plus vite. Il peut donc afficher l'ancienne version. Ctrl + F5 le force à tout retélécharger.

---

## 🟣 Exercice 6 — Espionner le navigateur

1. Que signifie HTTP ? Qui envoie la **requête** et qui envoie la **réponse** ?

   > _Ma réponse :_ HTTP signifie HyperText Transfer Protocol : c'est le langage de communication entre le navigateur et le serveur. Le navigateur envoie la requête, et le serveur envoie la réponse.

2. Combien de requêtes votre page `/presentation` a-t-elle déclenchées ? Lesquelles ?

   > _Ma réponse :_ Ma page /presentation a déclenché 3 requêtes : la page HTML (presentation), la feuille de style (style.css) et l'image du logo Python (Python-logo-notext.svg). Le navigateur lit d'abord le HTML, puis demande le CSS et l'image.

3. Que signifie le code `200` ? Et le code `404` de la favicon ?

   > _Ma réponse :_  Le code 200 veut dire que tout va bien : le serveur a trouvé la ressource et l'a envoyée. Le code 404 de la favicon (si on le voit) veut dire que le serveur n'a pas trouvé ce fichier, car mon site n'a pas d'icône.

4. Pourquoi les modifications faites dans l'onglet Éléments ne sont-elles pas visibles par les autres visiteurs ?

   > _Ma réponse :_  Les modifications dans l'onglet Éléments ne changent que la copie de la page qui est dans mon navigateur. Le serveur n'est pas modifié, et les autres visiteurs reçoivent toujours la version d'origine. Quand je recharge, mon navigateur redemande la page au serveur.

---

## 🟣 Exercice 7 — Envoyer des informations dans l'URL

1. Dans l'URL `https://www.youtube.com/results?search_query=chat`, quel est le nom du paramètre ? Quelle est sa valeur ?

   > _Ma réponse :_ Le nom du paramètre est search_query et sa valeur est chat.

2. Pourquoi le serveur plante-t-il avec `a=bonjour` ? Que faudrait-il faire pour l'éviter ?

   > _Ma réponse :_ Le serveur plante parce que int("bonjour") est impossible : "bonjour" n'est pas un nombre. Pour l'éviter, il faut vérifier la valeur avant de la convertir (par exemple avec try/except, ou avec isdigit()) et renvoyer un message d'erreur clair si ce n'est pas un nombre.

3. Pourquoi est-il dangereux d'afficher **tel quel** ce que l'utilisateur envoie ?

   > _Ma réponse :_ C'est dangereux parce que l'utilisateur peut envoyer du code HTML ou JavaScript qui sera exécuté dans le navigateur des autres visiteurs. Il faut toujours considérer ce que l'utilisateur envoie comme non fiable.

---

## 🟣 Exercice 8 — Les formulaires

1. Quelle est la différence visible entre GET et POST ?

   > _Ma réponse :_ 

2. Pour un formulaire de **recherche**, quelle méthode choisiriez-vous ? Et pour un formulaire de **connexion avec mot de passe** ? Pourquoi ?

   > _Ma réponse :_ 

3. Les données envoyées en POST sont-elles vraiment « secrètes » ? (Pensez à ce que vous avez vu dans l'onglet Réseau.)

   > _Ma réponse :_ 

---

## 🔴 Exercice 9 — Les codes de statut

1. Quelle est la différence entre une erreur `4xx` et une erreur `5xx` ? Qui est « fautif » dans chaque cas ?

   > _Ma réponse :_ 

2. Comment fonctionne une redirection ? Qui fait la deuxième requête : le serveur ou le navigateur ?

   > _Ma réponse :_ 

3. Donnez un exemple de situation où un vrai site utilise une redirection.

   > _Ma réponse :_ 

---

## 🔴 Exercice 10 — Ce que le serveur sait de vous

1. Citez trois informations que le serveur connaît sur vous, sans que vous ayez rien rempli.

   > _Ma réponse :_ 

2. À quoi peut servir l'en-tête `Accept-Language` pour un site comme Wikipédia ?

   > _Ma réponse :_ 

3. Dans l'Access log, retrouvez une requête qui a reçu un code `404`. Quelle page était demandée ?

   > _Ma réponse :_ 

4. Après cet exercice, que pensez-vous de la notion de « navigation anonyme » ?

   > _Ma réponse :_ 

---

## 🔴 Exercice 11 — Le Web des machines : API et JSON

1. Quelle est la différence entre une page HTML et une réponse JSON ? À qui chacune est-elle destinée ?

   > _Ma réponse :_ 

2. Dans la page `/horloge`, quel code s'exécute sur le **serveur** et quel code s'exécute dans le **navigateur** ?

   > _Ma réponse :_ 

3. Citez une application de votre téléphone qui, selon vous, utilise une API. Quelles données échange-t-elle ?

   > _Ma réponse :_ 

---

## 🏁 Pour conclure

En quelques phrases, expliquez à un ami ce qui se passe entre le moment où il tape une adresse dans son navigateur et celui où la page s'affiche :

> _Ma réponse :_ 
