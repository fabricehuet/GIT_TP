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

### Ça marche pas
1. Ajoutez à votre code un package fr.miage.bogus avec une classe qui *ne compile pas*.
2. Lancez la phase compile et analysez le message d'erreur
3. Dans le cas où corriger le code n'est pas immédiatement possible, on peut exclure du code de la compilation. Modifiez le pom.xml pour exclure le package bogus

### Dependances
1. Ajoutez à votre projet une dépendance vers ASCII Render
2. Écrivez une classe Dessin ayant des méthodes pour dessiner des formes géométriques simples (rectangle, carré....) avec ASCII Render
3. Ajoutez une méthode main et vérifiez le bon fonctionnement.

### Execution avec Maven
1. Trouvez comment exécuter une classe avec maven en passant son nom et d'autres paramètres sur la ligne de commande.
2. Modifiez votre pom.xml pour que l'exécution se fasse sans spécifier les paramètres comme précédemment.

### Resources
1. Ajoutez aux resources de votre projet un fichier config.cfg contenant quelques lignes de texte
2. Modifiez la classe Dessin pour qu'elle lise et affiche le contenu du fichier, sans utiliser de chemin absolu.

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
1. Creez un projet Maven et ajoutez les dépendances pour JUnit 5 à votre fichier pom.xml
2. Créez un unique test qui réussit tout le temps (utilisez par exemple assertTrue(true))
3. Testez avec Maven et commentez le résultat
4. Rajoutez un test qui échoue tout le temps et testez à nouveau

### Petite application
Dans cet exercice nous allons écrire une petite application découpée en deux modules. Cette application permet de calculer le résultat d'une opération arithmétique simple
sous la forme d'une chaine de caractères. Par exemple, si on a "25+5" alors elle retournera 30. Les opérations supportées sont les opérations arithmétiques de base et chaque chaine ne peut contenir qu'un opérateur.
Un module sera chargé de la partie calcul et l'autre des entrées sorties (lecture de fichiers texte). L'ensemble sera fait sous forme d'un projet Maven multi-modules et toutes les méthodes devront avoir des tests unitaires *exhaustifs*.
#### Module calcul
Une classe chargée du calcul contiendra au moins deux méthodes
- une méthode `boolean isValid(String)` qui vérifie qu'une chaine est une opération valide
- une méthode `int calcul(String)` qui retourne la valeur calculée
#### Module i/o
Une classe sera chargée de lire et écrire dans des fichiers texte
- `String[] readFromFile(String filename)` lira un fichier contenant plusieurs opérations, une par ligne
- `void writeResults(String filename, int[] results)` écrira dans un fichier les résultats, un par ligne.
