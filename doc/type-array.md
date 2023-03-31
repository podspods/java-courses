[< précédent](../README.md)

# Type Array

# Array

## création

création d'un tableau de 7 int (commence par 0 et fini à 6 )
note : le tableau de int est initialisé avec des zéros
le tableau de string est initialisé avec des null

```js
int[] bookCost = new int[7];
```

## création et initialisation

création d'un tableau (de taille automatique) et initialisé avec des valeurs  
note : le tableau est dimensionné par rapport au nombre de valeur ajouté

```js
String[] bookTitle = {"bootcamp at torcy","le seigneur des anneau"," star war","matrix I","matrix II" };
```

## affectation des valeurs et modification

pour le changement c'est pareil de l'affectation

```js
bookCost[1] = 10;
bookCost[2] = 87;

index = 3;
System.out.printf("bookCost at index %d value : %d\n", index, bookCost[index]);
System.out.printf(
  "book title at index %d value : %s\n",
  index,
  bookTitle[index]
);

bookCost[index] = 200;
bookTitle[index] = "Matrix tout court";

System.out.printf("bookCost at index %d value : %d\n", index, bookCost[index]);
System.out.printf(
  "book title at index %d value : %s\n",
  index,
  bookTitle[index]
);
```

## exemple complet

```js
public static void arrayTypeExample() {

    int[] bookCost = new int[7];
    String[] bookTitle = {"bootcamp at torcy","le seigneur des anneau"," star war","matrix I","matrix II" };
    String[] bookTitleVide = new String[2];

    bookCost[1] =10;
    bookCost[2] =87;
    bookCost[3] =99;
    bookCost[4] =499;
    bookCost[6] =699;

    int index = 0;
    System.out.printf("bookCost at index %d value : %d\n", index,bookCost[index] );
    System.out.printf("book title at index %d value : %s\n", index,bookTitle[index] );
    System.out.printf("book title at index %d value : %s\n", index,bookTitleVide[index] );

    index = 3;
    System.out.printf("bookCost at index %d value : %d\n", index,bookCost[index] );
    System.out.printf("book title at index %d value : %s\n", index,bookTitle[index] );

    bookCost[index] = 200;
    bookTitle[index] = "Matrix tout court";

    System.out.printf("bookCost at index %d value : %d\n", index,bookCost[index] );
    System.out.printf("book title at index %d value : %s\n", index,bookTitle[index] );

}
```
