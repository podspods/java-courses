# les fonctions

# voir méthdes

1. [Méthode de classe](./doc/class-methode.md)

# bonus

## nombre de paramètre variable

fonction avec le nombre de parametre variabe mais de même type

exemple

```java
public static void main(String[] args) {
    paramVariable(1,2,3,9,11);
}
public static void paramVariable(int ... tableauNbr) {

    int somme = 0 ;
    for (int nombre : tableauNbr ){
        somme += nombre;

    }
    System.out.printf (" somme %d \n", somme);

}
```

## lecture des paramètres d'appel variable

```js
// ---------------------------------------------------------------------------------
public static void main(String[] args) {
        parametre(args);
}

public static void parametre(String[] args) {
    int index = 0 ;
    for (String value : args){
        System.out.printf (" arg %d : arg %s\n", index , value);
        index++;
    }
}
```
