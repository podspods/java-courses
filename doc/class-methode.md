[< précédent](../README.md)

# Méthode de classe

# Définition

une méthode est une fonction dans une classe.

```java
  static void myMethod() {
     System.out.print("mY Method dans MyClass\n" ) ;
  }
```

1. `static` : veux dire que la méthode appartient à cette class. Ce n'est pas la méthode d'une autre (objet instancié) classe )
1. `void` : ne retourne rien
1. `myMethode` : nom de la méthode
1. entre les accolades {} c'est le corps de la méthode.

# Valeur de retour (return)

```java
static int myMethodReturn() {
     return 3;
  }
```

`int` : signifie que la méthode retourne un nombre entier

# Parametres

```java
static void myMethodParam(int param1) {
     System.out.printf("myMethodParam int: %d\n",param1 ) ;
  }
```

`int param1` : paramètre de type int dont le nom est param1
`void` : ne retourne rien

multi-paramètre mais toujours un seul return

```java
static String myMethodReturnAndParam(int param1, String text) {
     System.out.printf("myMethodReturnAndParam : %d\n",param1 ) ;
     System.out.printf("myMethodReturnAndParam : %s\n",text ) ;

     return String.format("texte : [%s] param1 :[%d]" , text, param1);
  }
```

ici `int param1, String text` sont des paramètres.

# Surcharge

```java
  static void myMethodParam(int param1) {
     System.out.printf("myMethodParam int: %d\n",param1 ) ;
  }
  static void myMethodParam(String param1) {
     System.out.printf("myMethodParam String : %s\n",param1 ) ;
  }
```

deux ou plusieurs méthodes peuvent porter le meme nom des lors que la liste des parametres sont différents

# Tout le code

```java
class  MyClass{

  static void myMethod() {
     System.out.print("mY Method dans MyClass\n" ) ;
  }
  static int myMethodReturn() {
     return 3;
  }
  static void myMethodParam(int param1) {
     System.out.printf("myMethodParam int: %d\n",param1 ) ;
  }
  static void myMethodParam(String param1) {
     System.out.printf("myMethodParam String : %s\n",param1 ) ;
  }

  static String myMethodReturnAndParam(int param1, String text) {
     System.out.printf("myMethodReturnAndParam : %d\n",param1 ) ;
     System.out.printf("myMethodReturnAndParam : %s\n",text ) ;

     return String.format("texte : [%s] param1 :[%d]" , text, param1);
  }


}
```
