[< précédent](../README.md)

# Java basic

1. [Hello word](#hello-word)
1. [compilation](#compilation)
1. [Exéctution](#exécution)
1. [Affichage console](#affichage-dans-la-console)
1. [Commentaire](#commentaire)

1. [formatage du texte](#formatage-du-texte)
1. [Opérateur](#opérateur-arithmétiques)
1. [Type de données](#type-de-variable)
1. [Constant](#constantes)
1. [Casting](#casting)

# Hello word

```java
public class Main {

    public static void main(String[] args) {
    }
}
```

Le nom de la class doit être le même que celui du fichier

# compilation

```sh
javac Main.java

```

# exécution

```sh
java Main
```

# affichage dans la console

```js
System.out.println("Texte");
```

# commentaire

Commentaire en ligne

```js
// ligne en commentaire
```

Commentaire en bloc

```js
/*
ligne en commentaire
ligne en commentaire aussi 
... en tout les autres jusqu'à la fin du bloc
*/
```

# formatage du texte

soit avec printf (comme en C)

```js
System.out.printf("nombre ->%d texte-> %s ", nombre, texte);
```

ou avec `String.format`

```js
String stringResult = String.format("my number ->%d my text-> %s ", nombre, texte);
System.out.println(stringResult);
```

# Opérateur arithmétiques

|  s  | opération      | exemple | résultat |
| :-: | :------------- | ------: | -------: |
|  +  | Addition       |     2+3 |        5 |
|  -  | Soustraction   |    12+3 |        9 |
| \*  | multiplication |    4\*3 |       14 |
|  /  | Division       |    13/3 |        4 |
|  %  | Modulo         |    16%3 |        1 |

# type de variable

| type    | taill | Description           | exemple                                     |
| ------- | ----- | --------------------- | ------------------------------------------- |
| boolean | 1     | booléen               | true ou false                               |
| byte    | 1     | octet (8bits)         | -128 à 127                                  |
| short   | 2     | nombre entier (petit) | -32,768 à 32,767                            |
| char    | 2     | caractère ASCII       | A,b, z                                      |
| int     | 4     | nombre entier         | -2,147,483,648 to 2,147,483,647             |
| float   | 4     | nombre 6 à 7 décimal  | 1.123456                                    |
| double  | 8     | nombre 15 décimal     | 1.123456789101112                           |
| long    | 8     | nombre entier         | -9223372036854775808 to 9223372036854775807 |

# constantes

Sont définiavec le mot clef « final ».

```js
final int maConstant = 123;

```

# casting

attention le casting ne fonctionne que pour les types compatibles
exemple : casting de string (avec des lettres) en int, risque de ne pas fonctionner

1. Widening Casting (automatically) converting a smaller type to a larger  
   type size byte -> short -> char -> int -> long -> float -> double

1. Narrowing Casting (manually) converting a larger type to a smaller size  
   type double -> float -> long -> int -> char -> short -> byte

```js
float myFloat = 10.2;
int myInt = (int) myFloat;
```
