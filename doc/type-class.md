[< précédent](../README.md)

# Type de donnée Classe

# règle

1. se déclare par le mot-clé class.
1. Déclaration de chaque classe dans un fichier à part; le nom du fichier est le nom de la class.
1. Seule la classe contenant main est exécutable:

## Creation de la class

1. type de class

| type    | description                                                                                              |
| ------- | -------------------------------------------------------------------------------------------------------- |
| public  | accessible par tout le monde doit être dans un fichier a part portant le nom de la class <nomClass.java> |
| default | la classe n'est accessible que par les class dans le même fichier (package)                              |

```js
class OtherClass{
    int valueInClass = 10 ;
}
```

## instancier la class

```js
    OtherClass monObjet = new OtherClass();
```

## modification

| type      | description                                                                 |
| --------- | --------------------------------------------------------------------------- |
| public    | accessible par tout le monde                                                |
| private   | accessible seulement dans la classe                                         |
| protected | accessible par les class dérivé et dans le même package                     |
| default   | la classe n'est accessible que par les class dans le même fichier (package) |

abstract, static, final etc.
[Plus d'information ici ](https://www.w3schools.com/java/java_modifiers.asp)

```js
monObjet.valueInClass++;
```

## utiliser

```js
System.out.printf(" mon objet : %d\n", monObjet.valueInClass);
```

## exemple complet

```js
class OtherClass{
    int valueInClass = 10 ;
}

public class Main {
    OtherClass monObjet = new OtherClass();
    System.out.printf(" mon objet : %d\n", monObjet.valueInClass);
    monObjet.valueInClass ++ ;
    System.out.printf(" mon objet++: %d\n", monObjet.valueInClass);
}
```
