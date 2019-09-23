# Mise en pratique de Maven et JUnit
Le but de ce TP est de se familiariser avec Maven et JUnit. Ce sont des outils complexes donc nous ne verrons qu'une partie de leurs possibilités.

Tout le TP doit être fait dans un répertoire sous contrôle de GIT. Les commits doivent être réguliers avec des messages pertinents.
## Maven
### Ça marche
1. Téléchargez et installez Maven sur votre machine
2. Assurez vous que vous avez un JDK >=8
3. Créez un projet Maven avec l'archétype maven-archetype-quickstart
4. Ouvrez le fichier pom.xml et commentez sa structure
5. Quelle est la structure du projet crée sur le disque ?
6. Créez une classe Main.java dans le package principal de votre projet avec un main(...) qui affiche juste un message
7. Invoquez la phase de compilation et vérifiez que tout se déroule correctement
8. Où sont placés les fichiers compilés ?
9. Utilisez Maven pour créer un jar. Où est-il placé ?
10. Maven peut être utilisé pour exécuter votre classe principale avec le plugin exec. Modifiez votre pom pour le faire.

### Ça marche pas
1. Ajoutez à votre code un package fr.miage.bogus avec une classe qui *ne compile pas*.
2. Lancez la phase compile et analysez le message d'erreur
3. Dans le cas où corriger le code n'est pas immédiatement possible, on peut exclure du code de la compilation. Modifiez le pom.xml pour exclure le package bogus

### Exécutable
1. Créez un jar exécutable de votre projet avec Maven.

### Modules
1. Créez un nouveau projet avec son pom.xml principal
2. Ajoutez deux modules `Utils` et `Afficheur` en créant les dossiers necessaires et leur fichiers pom.xml
3. Créez un package fr.miage.utils dans `Utils`, avec une classe qui contient la function `afficheHello()` qui simplement affiche "_Hello World!_"
4. Ajoutez au module `Afficheur` un package fr.miage.afficheur avec la class Main.class qui utilise la function `afficheHello()` du `module1` pour afficher l' _Hello World_
5. Compilez le projet et vérifiez que tout se déroule correctement

## Junit 5
### Simple
1. Ajoutez les dépendances pour JUnit 5 à votre fichier pom.xml
2. Modifiez votre pom.xml pour pouvoir compiler et générer du Java 8.
3. Créez un unique test qui réussit tout le temps (utilisez par exemple assertTrue(true))
4. Testez avec Maven et commentez le résultat
5. Rajoutez un test qui échoue tout le temps et testez à nouveau
