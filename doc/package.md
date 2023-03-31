[< précédent](../README.md)

# Package

Un package est un regroupement de `Class`.
Les packages peuvent provenir des API java ou créer

# import

pour importer un package avec une class explicite (recommandé)

```js
import package.name.Class;
```

pour importer toutes les class d'un package

```js
import package.name.*;
```

exemple

```js
import java.util.Scanner;

```

# Faire les package

1. faire une arborescence fichier equivalente à l'arborecence des package

## exemple

| nomProjet | arbo-1      | arbo-2     |
| --------- | ----------- | ---------- |
| nomProjet |             |            |
| l-------> | pack_pere_1 |            |
| l         | l----->     | pack_fils1 |
| l         | l----->     | pack_fils2 |
| l         | l----->     | pack_fils3 |
| l-------> | pack_pere_2 |            |

## liste des fichier

- nomProjet.java
- class-pere1.java
- class-fils1.java
- class-fils2.java
- class-fils3.java
- class-pere2.java

## contrainte

1. package pack_pere_1 contient :

   1. la classe class_pere_1.java
   1. le package pack_fils1
   1. le package pack_fils2
   1. le package pack_fils3

1. le package pack_fils1 contient
   1. la class class_fils1.java
1. le package pack_fils2
   1. la class class_fils2.java
1. le package pack_fils3

   1. la class class_fils3.java

1. package pack_pere_2 contient:
   1. la class class_pere2.java

## démarche

dans class_fils1.java

```java
package pack_pere_1.pack_fils1 ;

```

dans class_fils2.java

```java
package pack_pere_1.pack_fils2 ;

```

dans class_fils3.java

```java
package pack_pere_1.pack_fils3 ;

```

dans pack_pere_1.java

```java
package pack_pere_1 ;
import pack_pere_1.pack_fils1 ; // si besoin
import pack_pere_1.pack_fils2 ;// si besoin
import pack_pere_1.pack_fils3 ;// si besoin
```

dans pack_pere_2.java

```java
package pack_pere_2 ;
```

dans nomProjet.java

```java

import personage.Personage;
```

## compiler

compiler : lancer javac à partir de la racine du projet

```sh
javac pack_pere_1/pack_fils1
```

### bonus ave javac

Se mettre à la racine et faire

```sh
javac ./*.java  -d dist/
```

en faisant ./\*java, le compilateur commence par la class Main et remonter l'arborescence suivant les imports.  
! ca ne marche pas toujours

## faire le jar

```sh
cd dist
jar -cvf executable.jar *
```

## execution

```sh
java -cp executable.jar Main
```

## purge

purger tous les fichiers compilés \*.class (ubuntu)

```sh
find . -name "*.class" -type f -delete
```

## modification du manifest

editer le fichier ./META-INF/MANIFEST.MF dans executable.jar
ajouter `Main-Class: Main`  
et le remettre dans executable.jar

```js
Manifest-Version: 1.0
Created-By: 19.0.2 (Oracle Corporation)
Main-Class: Main
```

Clé `Class-Path` : L’option Class-Path permettra quant à elle de faire référence à d’autre .jar pour en importer les fonctionnalités.

autres clés du manifest.

| Clef                   | Description                         |
| ---------------------- | ----------------------------------- |
| Name                   | Nom du package                      |
| Specification-Title    | Titre de la specification           |
| Specification-Version  | Version de la spécification         |
| Specification-Vendor   | Vendeur de la spécification         |
| Implementation-Title   | Titre de l’implémentation           |
| Implementation-Version | Numéro de build de l’implémentation |
| Implementation-Vendor  | Vendeur de l’implémentation         |

## exécution

```sh
java -jar executable.jar
```

# exemple

## package

### déclaration du package

```java
package konsole;

```

### code complet

```java
package konsole;

public class Konsole{

    public static enum Color {BLACK,RED,GREEN,YELLOW,BLUE,PURPLE,CYAN,WHITE};

// ---------------------------------------------------------------------------------

    public static void  setCursor (int row, int column){
        char escCode = 0x1B;
        System.out.print(String.format("%c[%d;%df",escCode,row,column));
    }
// ---------------------------------------------------------------------------------
    public static void  clearScreen (){
        System.out.print("\033\143");
    }

    public static void  setColor (Color myColor){

        String choice = "\u001B[0m";
        switch (myColor){
            case BLACK : choice = "\u001B[30m"; break;
            case  RED : choice = "\u001B[31m"; break;
            case  GREEN : choice = "\u001B[32m"; break;
            case  YELLOW : choice = "\u001B[33m"; break;
            case  BLUE : choice = "\u001B[34m"; break;
            case  PURPLE : choice = "\u001B[35m"; break;
            case  CYAN : choice = "\u001B[36m"; break;
            case  WHITE: choice = "\u001B[37m"; break;
            default : choice = "\u001B[0m"; break;
        }
         System.out.print(choice);
    }

// fonction random qui renvoie une fonction entre minValue et maxValue
// attention dans le cas de l'utilisation pour indexer un tableau (maxIndex = length)
    public static int randInt(int minValue, int maxValue) {
        // minvalue er maxValue inclus
        return   (int)(Math.random() * (maxValue + 1-minValue) + minValue );
    }


}
```

## utilisaton du package

### utilisation du type énuméré du package

```java
    Konsole.setColor (Konsole.Color.YELLOW);
```

### utilisation de la méthode randInt du package

```java
  if (Konsole.randInt(0,1)==0){
```

### code complet

```java
import java.util.Scanner;
import java.lang.Math;
import java.util.ArrayList;
import java.util.Iterator;
import konsole.Konsole;
// ----------------------------------------------------------------------------
public class Main {
// ----------------------------------------------------------------------------
    public static int template(String reponse) {
        return 0;
    }
// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    public static void main(String[] args) {
            Scanner myScan = new Scanner(System.in);
            System.out.println("hello de lu");
            Konsole.setColor (Konsole.Color.YELLOW);

    // 1. Créer un ensemble de 6 Rectangles ou Carrés aux cotés aléatoires (entree 2 et 10)
        ArrayList<Rectangle> rectangleList = new ArrayList<Rectangle>();

        for (int index = 0 ; index < 6 ; index ++){
            Rectangle myForm ;

            if (Konsole.randInt(0,1)==0){
                myForm = new Rectangle(Konsole.randInt(1,10),Konsole.randInt(1,10));
            }
            else{
                myForm = new Carre(Konsole.randInt(1,10));

            }

            rectangleList.add( myForm);
        }


    // 4. Utiliser les méthode (2) et (3) sur notre ensemble de Rectangles et Carré (et afficher les résultats)

        int resultPerimeter = computeTotalPerimeter(rectangleList);
        int resultArea = computeTotalAera(rectangleList);
        display(rectangleList);
        System.out.printf("Total Perimeter : %d Total Area %s \n",resultPerimeter,resultArea);


    }

// ---------------------------------------------------------------------------------

    // 2. Créer une méthode dans Main permettant de calculer la somme des périmétres d'un ensemble de formes
    public static int  computeTotalAera(ArrayList<Rectangle> formList) {
        // using iterator
        Iterator <Rectangle> myIterator =formList.iterator();
        int returnValue = 0 ;
        while (myIterator.hasNext())
        {

           returnValue+= myIterator.next().aire();

        }
        return returnValue;
    }
// ---------------------------------------------------------------------------------

    // 2. Créer une méthode dans Main permettant de calculer la somme des périmétres d'un ensemble de formes
    public static int  computeTotalPerimeter(ArrayList<Rectangle> formList) {
        // not using iterator : regular method
        int returnValue = 0 ;
        for ( Rectangle myForm : formList)
        {
            returnValue+= myForm.perimetre();
        }
        return returnValue;
    }
// ---------------------------------------------------------------------------------
    public static void display (ArrayList<Rectangle> formList) {

        for ( Rectangle myForm : formList)
        {
            System.out.printf("%s\n",myForm);
        }
    }


// ---------------------------------------------------------------------------------
    public static void display2 (ArrayList<Rectangle> formList) {
        Iterator <Rectangle> myIterator =formList.iterator();


        while (myIterator.hasNext())
        {

         System.out.printf("%s\n",myIterator.next());

        }
    }


// ---------------------------------------------------------------------------------

   public static void testMain() {
     // 2. Dans le main, créer un rectangle r1 de 9 de longeur et de 6 de largeur
    //     2.1 Afficher son périmétre et son aire
        Rectangle r1 = new Rectangle(9,6);

        System.out.println(r1);

        Rectangle r2 = new Rectangle(r1);
        System.out.println(r2);

        // 3.2 Créer un carré c1, de coté 12, dont on affichera le périmétre et l'aire

        Carre c1 = new Carre(12);
        System.out.println(c1);

        Carre c2 = new Carre(c1);
        System.out.println(c2);

   }


// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
}
   // 1. Créer une classe Rectangle
class Rectangle{

    //     1.1 Elle dispose des attributs largeur et longeur
    private int largeur;
    private int longeur;


    //     1.2 Respecter l'encapsulation et ajouter un constructeur prenant en paramètre la largeur et la longeur

    Rectangle(int myLong, int myLarg){
        this.setLongeur(myLong) ;
        this.setLargeur(myLarg) ;
    }
    Rectangle (Rectangle newRectangle){
        this (
            newRectangle.getLongeur(),
            newRectangle.getLargeur()
        );
    }


    public int getLongeur(){
        return this.longeur;
    }
    public void setLongeur(int myLong){
        this.longeur = myLong;
    }

    public int getLargeur(){
        return this.largeur;
    }
    public void setLargeur(int myLarg){
        this.largeur = myLarg;
    }

    //     1.3 Lui ajouter la méthode périmétre (retourne le périmétre du rectangle : (longeur + largeur) * 2)
    public int perimetre(){
        return
        (this.getLargeur() + this.getLongeur()) *2
        ;
    }

    //     1.4 Lui ajouter la méthode aire (retourne l'aire du rectangle : (longeur * largeur) )
    public int aire(){
        return (this.getLargeur() * this.getLongeur() );
    }

    public  String toString() {
        return String.format ("Rectangle longueur: %2d largeur : %2d périmètre %2d aire %3d ",
        this.getLongeur(),this.getLargeur(),this.perimetre(),this.aire());

    }


}

    // 3. Créer une classe Carre

class Carre extends Rectangle {
        // 3.1 Lui ajouter un constructeur ne prenant qu'un unique paramètre coté, faisant appel au constructeur du rectangle
    Carre (int cote){
        super( cote, cote);
    }

    Carre (Carre carreCopi){
        this ( carreCopi.getLargeur()  );
    }
    public  String toString() {
        return String.format ("Carre        coté : %2d              périmètre %2d aire %3d ",
        this.getLargeur(),this.perimetre(),this.aire());

    }

}


```
