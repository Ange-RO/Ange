1/25
Quel est le but de la méthode 'finalize' en Java ?

Pour initialiser des variables

Pour nettoyer des ressources avant que l'objet soit collecté par le Garbage Collector

Pour finaliser une définition de classe

Pour finaliser des affectations de variables

2/25
Que signifie le mot-clé 'transient' dans une classe Java ?

La variable peut être sérialisée

La variable est thread-safe

La variable ne peut pas être sérialisée

La variable est volatile

En Java, quelle est la manière correcte de créer un thread ?

En implémentant l'interface Runnable

En étendant la classe Thread

En étendant l'interface Runnable

En implémentant la classe Thread

4/25
Quelle classe de collection en Java est synchronisée ?

ArrayList

LinkedList

Vector

HashSet


5/25
Quel est le résultat du code Java suivant ?
int[] array = {1, 2, 3};
System.out.println(array[3]);

3

Une ArrayIndexOutOfBoundsException est lancée

null

0


6/25
Quel est l'objectif principal du mot-clé 'super' en Java ?

Pour appeler une méthode de la classe parente

Pour déclarer des variables

Pour créer une nouvelle instance de la classe parente

Pour remplacer une méthode dans la classe enfant


7/25
Quelle est la valeur par défaut d'une variable statique en Java ?

0 ou null, selon le type

1

undefined

Elle n'a pas de valeur par défaut

8/25
Quelle méthode est appelée lorsqu'un objet est cloné en Java ?

cloneMethod()

copy()

clone()

Object.clone()


9/25
À quoi sert le mot-clé 'final' en Java ?

Pour finaliser la création d'un objet

Pour créer une variable ou méthode constante

Pour indiquer la dernière classe dans une hiérarchie

Pour finaliser des affectations de variables

10/25
Quelle fonctionnalité Java permet à la méthode d'une sous-classe de remplacer la méthode de sa superclasse ?

L'héritage

L'encapsulation

Le polymorphisme

L'abstraction


11/25
Quel est le type de retour de la méthode hashCode() en Java ?

Object

long

int

String

12/25
Quelle exception est lancée lorsqu'on essaie d'accéder à un élément avec une clé qui n'existe pas dans une HashMap ?

NullPointerException

ArrayIndexOutOfBoundsException

KeyNotFoundException

NoSuchElementException


13/25
Lequel des énoncés suivants est vrai à propos d'une classe 'final' en Java ?

Elle peut être étendue par d'autres classes

Elle ne peut pas être instanciée

Elle ne peut avoir que des méthodes finales

Elle ne peut pas être étendue par d'autres classes

14/25
Quel est le rôle de l'instruction 'import' en Java ?

Pour inclure un paquet dans le fichier courant

Pour exporter une classe vers un autre fichier

Pour charger une bibliothèque au moment de l'exécution

Pour déclarer une variable


15/25
Quel est l'usage d'un 'JFrame' en Java ?

Pour créer une application basée sur la console

Pour créer une fenêtre d'interface graphique

Pour gérer les connexions à la base de données

Pour stocker des données dans un fichier

16/25
Comment déclarez-vous une variable constante en Java ?

En utilisant le mot-clé 'constant'

En utilisant les mots-clés 'static final'

En utilisant le mot-clé 'immutable'

En déclarant sans initialisation

17/25
Qu'est-ce qu'un thread 'daemon' en Java ?

Un thread à haute priorité

Un thread qui s'exécute en arrière-plan

Un thread qui ne peut pas être tué

Le thread principal d'une application


18/25
Lequel des éléments suivants est une exception vérifiée en Java ?

NullPointerException

ArrayIndexOutOfBoundsException

IOException

RuntimeException

19/25
Quelle est la principale différence entre 'StringBuffer' et 'StringBuilder' en Java ?

StringBuffer est mutable, tandis que StringBuilder est immuable

StringBuilder est plus rapide car il n'est pas synchronisé

StringBuffer peut stocker des caractères, tandis que StringBuilder ne le peut pas

StringBuilder est thread-safe, tandis que StringBuffer ne l'est pas

20/25
Quelle est la différence entre les méthodes 'static' et 'non-static' en Java ?

Les méthodes statiques peuvent être appelées sans créer une instance de la classe

Les méthodes non-statiques sont toujours synchronisées

Les méthodes statiques sont plus rapides

Les méthodes non-statiques peuvent accéder à n'importe quelle variable de classe


21/25
Qu'est-ce qu'un 'JavaBean' ?

Une bibliothèque Java pour développer des applications Web

Un composant logiciel réutilisable qui suit certaines conventions de conception

Un type de variable Java

Un outil pour gérer les paquets Java


22/25
En Java, qu'est-ce qu'une 'exception vérifiée' ?

Une exception qui est vérifiée au moment de la compilation

Une exception qui est vérifiée uniquement à l'exécution

N'importe quelle exception qui se produit pendant l'exécution du programme

Une exception qui ne peut pas être attrapée ou gérée


23/25
Que signifie le mot-clé 'final' lorsqu'il est appliqué à une méthode en Java ?

La méthode peut être surchargée dans une sous-classe

La méthode ne peut pas être surchargée dans une sous-classe

La méthode renverra une valeur finale

La méthode sera exécutée à la fin du programme


24/25
Quelle est la principale différence entre une classe Java et une interface Java ?

Une classe définit les propriétés d'un objet, une interface définit le comportement d'un objet

Une classe peut être instanciée, mais une interface ne peut pas

Les interfaces prennent en charge l'héritage multiple, les classes ne le font pas

Une classe est utilisée pour l'implémentation, une interface est utilisée pour l'abstraction


25/25
Qu'est-ce que 'JDBC' en Java ?

Java Database Connectivity, une API standard pour l'accès aux bases de données

Java Data Binding Code, un framework pour lier des données aux éléments de l'interface utilisateur

Just-in-time Database Compiler, un outil pour l'optimisation des bases de données

Java Deployment and Compilation, un outil de déploiement



reponse


Voici les réponses aux questions posées :

1/25
**Quel est le but de la méthode 'finalize' en Java ?**
- Pour nettoyer des ressources avant que l'objet soit collecté par le Garbage Collector

2/25
**Que signifie le mot-clé 'transient' dans une classe Java ?**
- La variable ne peut pas être sérialisée

3/25
**En Java, quelle est la manière correcte de créer un thread ?**
- En implémentant l'interface Runnable
- **ou** En étendant la classe Thread (les deux méthodes sont valides)

4/25
**Quelle classe de collection en Java est synchronisée ?**
- Vector

5/25
**Quel est le résultat du code Java suivant ?**
```java
int[] array = {1, 2, 3};
System.out.println(array[3]);
```
- Une ArrayIndexOutOfBoundsException est lancée

6/25
**Quel est l'objectif principal du mot-clé 'super' en Java ?**
- Pour appeler une méthode de la classe parente

7/25
**Quelle est la valeur par défaut d'une variable statique en Java ?**
- 0 ou null, selon le type

8/25
**Quelle méthode est appelée lorsqu'un objet est cloné en Java ?**
- Object.clone()

9/25
**À quoi sert le mot-clé 'final' en Java ?**
- Pour créer une variable ou méthode constante

10/25
**Quelle fonctionnalité Java permet à la méthode d'une sous-classe de remplacer la méthode de sa superclasse ?**
- Le polymorphisme

11/25
**Quel est le type de retour de la méthode hashCode() en Java ?**
- int

12/25
**Quelle exception est lancée lorsqu'on essaie d'accéder à un élément avec une clé qui n'existe pas dans une HashMap ?**
- NullPointerException

13/25
**Lequel des énoncés suivants est vrai à propos d'une classe 'final' en Java ?**
- Elle ne peut pas être étendue par d'autres classes

14/25
**Quel est le rôle de l'instruction 'import' en Java ?**
- Pour inclure un paquet dans le fichier courant

15/25
**Quel est l'usage d'un 'JFrame' en Java ?**
- Pour créer une fenêtre d'interface graphique

16/25
**Comment déclarez-vous une variable constante en Java ?**
- En utilisant les mots-clés 'static final'

17/25
**Qu'est-ce qu'un thread 'daemon' en Java ?**
- Un thread qui s'exécute en arrière-plan

18/25
**Lequel des éléments suivants est une exception vérifiée en Java ?**
- IOException

19/25
**Quelle est la principale différence entre 'StringBuffer' et 'StringBuilder' en Java ?**
- StringBuilder est plus rapide car il n'est pas synchronisé

20/25
**Quelle est la différence entre les méthodes 'static' et 'non-static' en Java ?**
- Les méthodes statiques peuvent être appelées sans créer une instance de la classe

21/25
**Qu'est-ce qu'un 'JavaBean' ?**
- Un composant logiciel réutilisable qui suit certaines conventions de conception

22/25
**En Java, qu'est-ce qu'une 'exception vérifiée' ?**
- Une exception qui est vérifiée au moment de la compilation

23/25
**Que signifie le mot-clé 'final' lorsqu'il est appliqué à une méthode en Java ?**
- La méthode ne peut pas être surchargée dans une sous-classe

24/25
**Quelle est la principale différence entre une classe Java et une interface Java ?**
- Les interfaces prennent en charge l'héritage multiple, les classes ne le font pas

25/25
**Qu'est-ce que 'JDBC' en Java ?**
- Java Database Connectivity, une API standard pour l'accès aux bases de données