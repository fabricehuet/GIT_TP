# Mise en pratique de GIT
Le but de ce TP est de se familiariser avec GIT dans les différents modes qu'il offre. Toutes les commandes doivent se faire dans un terminal. Vous devez les **copier** dans fichier txt pour pouvoir les rejouer rapidement en cas de problème.

## Git Local
### Simple
1. Si vous n'avez jamais utilisé git sur votre machine, configurez le nom et l'email pour faire des commits
2. Créez un répository local dans un repertoire __repo1__
3. Que contient ce répertoire après l'initialisation ?
4. Créez les répertoires _src_ et _bin_ à la racine de votre copie locale, ajoutez les à GIT et faites un commit. Expliquez le résultat.

### Basique
1. Créez un fichier source pour la classe Java _fr.miage.votrenom.Hello_ dans _src_. Sans taper aucune commande GIT de modification de l'index, regardez l'état de votre copie locale. Expliquez le résultat.
2. Ajoutez le fichier à l'index __SANS__ faire de commit ensuite. Demandez à voir l'état et expliquez le résultat.
3. Faites un commit et vérifiez l'état.

### Delete
1. Compilez votre code Java et placez le résultat dans _bin_  (vous pouvez utiliser un IDE)
2. Ajoutez le fichier _.class_ généré et commitez.
3. Vous réalisez après le commit que c'était une mauvaise idée. Supprimez le du dépôt avec la commande git adéquate.

### Pollution
1. Notez la taille du répertoire _.git_
2. Trouvez un fichier de quelques Mo, placez le dans _bin_ et ajoutez le au dépôt.
3. Quelle est maintenant la taille du répertoire _.git_. Expliquez.
4. Copiez le fichier ajouté sous un autre nom et ajoutez le lui aussi au dépôt.
5. Quelle est maintenant la taille du répertoire _.git_. Expliquez.
6. Supprimez les deux fichiers du dépôt.
7. Quelle est maintenant la taille du répertoire _.git_. Expliquez.
8. Demandez les logs et vérifiez que les opérations d'ajout et de suppression des fichiers ont bien donné lieu à des commits. Quels sont leur SHA1 ?

L'ajout de ces fichiers était une erreur, nous les avons supprimé. Le problème est que ça pollue les logs avec des informations non pertinentes.
Nous allons maintenant apprendre à ré-écrire le passé. Il s'agit d'une opération __DANGEREUSE__ qu'il n'est pas possible d'annuler.

### Ré-écrire l'histoire
1. Idenfiez le SHA1 correspondant au dernier __avant__ l'ajout des fichiers.
2. Forcez un _hard reset_ au commit précédemment trouvé
3. Vérifiez que _HEAD_ pointe maintenant vers ce nouveau commit
4. Quelle est la taille de _.git_. Cherchez une explication.

### Branche tout va bien
1. Dans quelle branche travaillez vous par défaut ?
2. Créez une branche _br1_
3. Dans quelle branche vous trouvez vous ? Changez pour _br1_
4. Ajoutez une classe Java _fr.miage.votrenom.AdvancedHello_ dans _src_ et commitez la.
5. Regardez le log et commentez le dernier commit
6. Repassez dans la branche _master_ et regarder le contenu de _src_. Où est votre nouvelle classe ?
7. Dans _master_, modifiez la classe _fr.miage.votrenom.Hello_ pour ajouter une méthode _main_ avec un _println("Hello")_. Commitez la.
8. Repassez dans _br1_. La modification est-elle visible ?
9. Depuis _br1_, fusionnez _master_ et vérifiez que vous avez les modifications.
10. Regardez le log de commit, comment est indiqué le merge ?
11. Repassez dans _master_ et vérifiez si toutes les modifications sont présentes. Qu'en conclure sur l'opération de merge ?

### Branche tout va moins bien
1. Créez une nouvelle branche _br2_
2. Dans _br2_, modifiez _println("Hello")_ avec une _String_ de votre choix et commitez le résultat.
3. Dans _master_ modifiez  _println("Hello")_ avec une autre  _String_ de votre choix et commitez le résultat.
4. Dans _br2_ faites un merge avec _master_. Vous devriez avoir un conflit, vérifiez avec statu que c'est bien le cas.
5. Corrigez le conflit et faites un commit.

## Git Local avec bare repository
Pour cet exercice vous aurez besoin de 3 terminaux ouverts en même temps pour taper les différentes commandes. Un terminal sera sur le _bare repository_ (BR), et
les deux autres représenteront deux utilisateurs (U1 et U2).

### Simple
1. Dans _BR_ créez un répertoire _bare_ dans lequel vous initialiserez un _bare repository_
2. Dans _U1_ clonez le dépôt. Quel message d'avertissement avez vous ?
3. Dans _U1_ ajoutez un fichier et commitez.
4. Vérifiez le status, quel est le message d'avertissement, pourquoi ?
5. Poussez les modifications et vérifiez le status.

### Basic
1. Dans _U2_ clonez _bare_
2. Dans _U2_ ajoutez et commitez un nouveau fichier *sans* le pousser
3. Dans _U1_ faites un pull, est-ce que le nouveau fichier est visible ?
4. Que doit faire _U2_ pour que ses modifications soient visibles ? Faites le.
5. Dans _U2_ créez une branche _br_ et ajoutez/commitez un fichier dedans.
6. Que se passe-t-il quand vous essayez de pousser vos changements ?
7. Utilisez la commande suggérée pour pousser votre Branche
8. Dans _U1_ récupérez la nouvelle branche et vérifiez que vous avez bien tous les fichiers.

## Git Distant
Reprenez l'exercice précédent en ayant cette fois _bare_ hébergé dans un service spécialisé comme GitHub ou BitBucket.

## Play fun games, win totally virtual prizes
https://learngitbranching.js.org/

## Question Git de la mort
1. Quel est le ?
