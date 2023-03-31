[< précédent](../README.md)

# Récursivité

L'exemple addition les nombres

la fonction s'appelle elle-meme tant que la valeur d'itération n'est pas atteint

# mécanisme

```java
return iteration +resursive (iteration-1);
```

retourne la valeur de l'itération et rappelle la foncton avec le nombre de récursivité -1

# condition de sortie

```js
if (iteration > 0 ){
```

# valeur de sortie

```js
   }else { return 0 ; }
```

tant que supérieur à 0 on continue

# Tout le code

```java
public static void main(String[] args) {

        // exempleHeritageClass();
        //  exercice11();
         int result = resursive(10);
           System.out.printf("itération : %d\n",iteration ) ;
    }

 public static int resursive(int iteration) {

        if (iteration > 0 ){
            System.out.printf("itération : %d\n",iteration ) ;
            return iteration +resursive (iteration-1);
        }else { return 0 ; }

    }
```
