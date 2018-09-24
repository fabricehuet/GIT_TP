# Mise en pratique de GIT
Le but de ce TP est de se familiariser avec GIT dans les différents modes qu'il offre. Toutes les commandes doivent se faire dans un terminal. Vous devez les **copier** dans fichier txt pour pouvoir les rejouer rapidement en cas de problème.

## Git Local
### Simple
1. Créez un répository local dans un repertoire __repo1__
2. Que contient ce répertoire après l'initialisation ?
3. Créez les répertoires _src_ et _bin_ à la racine de votre copie locale, ajoutez les à GIT et faites un commit. Expliquez le résultat.

### Basique
1. Créez un fichier source pour la classe Java _fr.miage.votrenom.Hello_ dans _src_. Sans taper aucune commande GIT, regardez l'état de votre copie locale. Expliquez le résultat.
2. Ajoutez le fichier à l'index __SANS__ faire de commit ensuite. Demandez à voir l'état et expliquez le résultat.
3. Faites un commit et vérifiez l'état.

### Delete
1. Compilez votre code Java et placez le résultat dans _bin_  (vous pouvez utiliser un IDE)
2. Ajoutez le fichier _.class_ généré et commitez.
3. Vous réalisez après le commit que c'était une mauvaise idée. Supprimez le du dépot avec la commande git adéquate.

### Polution
1. Notez la taille du répertoire _.git_
2. Trouvez un fichier de quelques Mo, placez le dans _bin_ et ajoutez le au dépot.
3. Quelle est maintenant la taille du répertoire _.git_. Expliquez.
4. Copiez le fichier ajouté sous un autre nom et ajoutez le lui aussi au dépot.
5. Quelle est maintenant la taille du répertoire _.git_. Expliquez.
6. Supprimez les deux fichiers du dépot.
7. Quelle est maintenant la taille du répertoire _.git_. Expliquez.
8. Demandez les logs et vérifiez que les opérations d'ajout et de suppression des fichiers ont bien donné lieu à des commits. Quels sont leur SHA1 ?

L'ajout de ces fichiers était une erreur, nous les avons supprimé. Le problème est que ça pollue les logs avec des informations non pertinantes.
Nous allons maintenant apprendre à ré-écrire le passé. Il s'agit d'une opération __DANGEREUSE__ qu'il n'est pas possible d'annuler.

### Ré-écrire l'histoire
1. Idenfiez le SHA1 correspondant au dernier __avant__ l'ajout des fichiers.
2. Forcez un _hard reset_ au commit précédemment trouvé
3. Vérifiez que _HEAD_ pointe maintenant vers ce nouveau commit
4. Quelle est la taille de _.git_. Cherchez une explication. 


## Git Local avec bare repository


## Git Distant
