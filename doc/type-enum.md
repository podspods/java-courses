[< précédent](../README.md)

# Type Enum

Type énuméré

# règles

Par convention les valeurs sont en majuscule (comme pour les constantes)

```js
enum ColorEnum {
        ROUGE,
        BLEU,
        VERT,
        MARRON,
        JAUNE,
        violet
        }
```

Au dessus , ca marche mais ce n'est pas dans les règles de
lisibilité.
En dessous c'est mieux

```js
enum ColorEnum {
        ROUGE,
        BLEU,
        VERT,
        MARRON,
        JAUNE,
        VIOLET
        }
```

déclaration de la variable de type enum

```js
ColorEnum myLevel ;

```

Affectation de la valeur dans la variable

```js
myLevel = ColorEnum.VIOLET;
```

# tout le code

```java
   public static void typeEnum() {
            // value lmust be in uppercase
        enum ColorEnum {
        ROUGE,
        BLEU,
        VERT,
        MARRON,
        JAUNE,
        violet
        }

        ColorEnum myLevel ;

        myLevel = ColorEnum.ROUGE;
        myLevel = ColorEnum.VIOLET;
        // myLevel = ColorEnum.violet;

        System.out.printf(" s[%s] \n",myLevel);

    }
```
