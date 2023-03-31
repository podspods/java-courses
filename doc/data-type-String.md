[< précédent](../README.md)

# Data type String

Ce n'est pas un type primitif
[La doc est ici](https://www.w3schools.com/java/java_ref_string.asp)

# creation

```js
String myString = "sAy SoMeThInG weird or not";          // creation
```

# Taille de la chaine de caractere

```js
int myStringSize = myString.length() ;
System.out.printf("longueur : %d\n",myStringSize );  // affiche la longueur
```

# fonction Majuscule

```js
String myUpperString = myString.toUpperCase();
System.out.printf("tout en majuscule  : %s\n",myUpperString );  // affiche la longueur
```

# fonction Minuscule

```js
String myLowerString = myString.toLowerCase();
System.out.printf("tout en minuscule : %s\n", myLowerString);  // affiche la longueur
```

# fonction position

```js
StringordLoopAt = "or";
int position = myString.indexOf(wordLoopAt);
System.out.printf("le mot \"%s\" commence à la position : %d\n" wordLoopAt,position );  // affiche la longueur
```

[tous les autres fonctionnalité de String est ici](https://www.w3schools.com/java/java_ref_string.asp)

# Exemple complet

```js
public static void exempleString() {


        String myString = "sAy SoMeThInG weird or not";          // creation
        System.out.printf("voici la String : %s\n", myString);  // affiche la longueur
        System.out.printf("longueur : %d\n", myString.length());  // affiche la longueur

        System.out.printf("tout en majuscule  : %s\n", myString.toUpperCase());  // affiche la longueur
        System.out.printf("tout en minuscule : %s\n", myString.toLowerCase());  // affiche la longueur

        System.out.printf("index est : %d\n", myString.indexOf("or"));  // affiche la longueur

        String prenom = "indiana";
        String nom = "jones";

        System.out.println("mon nom est "+ prenom + " " + nom) ;

    }
```
