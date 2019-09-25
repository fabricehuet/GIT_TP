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
- une méthode _boolean isValid(String)_ qui vérifie qu'une chaine est une opération valide
- une méthode _int calcul(String)_ qui retourne la valeur calculée
#### Module i/o
Une classe sera chargée de lire et écrire dans des fichiers texte
- _String[] readFromFile(String filename)_ lira un fichier contenant plusieurs opérations, une par ligne
- _void writeResults(String filename, int[] results)_ écrira dans un fichier les résultats, un par ligne.
