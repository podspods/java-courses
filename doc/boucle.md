[< précédent](../README.md)

# Java Boucle

1. [while](#boucle-while)
1. [do-while](#boucle-do-while)
1. [for](#boucle-for)
1. [for-each](#boucle-for-each)
1. [break, continue ](#boucle-for-each)

# boucle while

## condition de sortie

- tant que cette condition est vrai on boucle.
- nombre de boucle = 0 à n

```java
while (nombreIteration <tailleTableau )
```

## tout le code

```java
int nombreIteration = 0 ;
while (nombreIteration <tailleTableau ){

    System.out.printf(" votre nombre nb %d ? :", nombreIteration ) ;
    myCalcArray[nombreIteration] =  myScan.nextInt();
    // myScan.nextLine();
    nombreIteration++;
}
```

# boucle do-while

## condition de sortie

- on boucle jusqu'a ce que la condition devient fausse
- nombre de boucle = 1 à n

```java
  }while (motDePass.compareTo("toto195")!=0 );
```

```java
 do {

            // 1. Demander à l'utilisateur de rentrer un mot de passe
            System.out.print("mot de pass svp :" ) ;
            motDePass = myScan.nextLine();



        }while (motDePass.compareTo("toto195")!=0 );
```

# boucle for

## condition de départ

initialisation de la boucle : se fait une seul fois

```java
 for (int index = 0 ;...;...)
```

## condition de sorti

test à chaque fin de boucle s'il y faut réitéré au pas.

```java
 for (.. ; index < myIntArray.length ;...)
```

## changement de la consigne à chaque tour

changement de la condition de boucle

```java
for (... ; ... ; index++){
```

## tout le code

```java
for (int index = 0 ; index < myIntArray.length ; index++){
    if ((myIntArray[index]%2) ==0 ){
        System.out.printf("tableau[%d] = %d\n", index,  myIntArray[index] ) ;
        result+=myIntArray[index] ;
    }
}
```

# boucle "for-each"

## condition de sortie

boucle sur tout le tableau et gère l'index .

```java
for ( int myInt : myIntArray ){
    System.out.printf("for each  [%d]\n", myInt  ) ;
}
```

# Break-Continue

Lors de l’exécution d’une structure itérative,
while ou for, il sera possible d’utiliser les
instructions break et continue.
L’instruction break, lorsqu’elle sera
interrompra la boucle dans sa totalité.
lue,
Cela signifie donc que l’on passera directement
aux instructions suivant la boucle.

## break

le break termine la boucle

```js
 for (int value : myIntArray){
        if (value == 22 )
            break;
        System.out.printf(" [%d] \n",value);
    }
```

## continue

le continue termine l'itération en cours

```js
    for (int value : myIntArray){
        if (value == 22 )
            continue;
        System.out.printf(" [%d] \n",value);
    }

```

## tout le code

```js
public static void breakContinue() {
    int[] myIntArray = {1,34,4,5,10,2,22,87} ;
    for (int value : myIntArray){
        System.out.printf(" [%d] \n",value);
    }
    System.out.printf("*** break à 22*** \n");
    for (int value : myIntArray){
        if (value == 22 )
            break;
        System.out.printf(" [%d] \n",value);
    }
    System.out.printf("*** continue à 22*** \n");
    for (int value : myIntArray){
        if (value == 22 )
            continue;
        System.out.printf(" [%d] \n",value);
    }
}
```
