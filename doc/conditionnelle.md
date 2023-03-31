[< précédent](../README.md)

# Structures conditionnelles

# Conditions

| opérateur | Signification         | Exemple     | Valeur |
| --------- | --------------------- | ----------- | ------ |
| ==        | Egalité               | 41 == 62    | False  |
| !=        | Inégalité             | 41 != 62    | True   |
| >         | Strictement supérieur | 10 > 5      | True   |
| <         | Strictement inférieur | 10 < 5      | False  |
| > =       | Supérieur ou égal     | 11 >= 5 + 6 | True   |
| <=        | Inférieur ou égal     | 11 <= 5 - 3 | True   |

# Combinaisons logiques

| opérateur | Signification | Exemple                  | Valeur |
| --------- | ------------- | ------------------------ | ------ |
| &&        | Et            | 10 == 10 && 5 > 6        | False  |
| \|\|      | Ou            | 10 == 10 \|\| 5 > 6 True |
| !         | Inverse       | !10 == 10                |

# Structure IF

```js
if (condition) {
  instruction();
}
```

```js
 public static void exempleIf() {
    Scanner keyb = new Scanner(System.in);

    System.out.print("age ?: ");
    int age = keyb.nextInt();

    System.out.print("nom ?: ");
    keyb.nextLine();

    String nom = keyb.nextLine();

    if (isMajeur(age)) {
        System.out.printf("l'individue %s est majeur\n ", nom);
    } else {
        System.out.printf("l'individue %s n'est pas majeur\n ", nom);

    }
    keyb.close();

}
```

# Structure Switch

```js
public static void exempleSwitch() {

    Scanner keyb = new Scanner(System.in);

    System.out.print("choix ? [1,2 ou 3] :");
    int choix = keyb.nextInt();
    switch (choix) {
        case 1:
            System.out.printf("votre choix %d \n", choix);
            break;
        case 2:
            System.out.printf("votre choix %d \n", choix);
            break;
        case 3:
            System.out.printf("votre choix %d \n", choix);
            break;
        default:
            System.out.printf("choix %d n'est pas possible\n", choix);
            break;
    }
keyb.close();

}
```

# Opérateur ternaire

comme en C ou javascript

```js
Condition ? Valeur si vrai : Valeur si faux ;s
```

exemple détaillé

```js
public static String exempleTernaire(int nombre) {

    boolean testTernaire ;
    testTernaire = (nombre >0);
    String valeurPourTrue = "supérieur à zéro";
    String valeurPourFalse = "inférieur ou égale zéro";

    return (  testTernaire ? valeurPourTrue : valeurPourFalse);

}
```

exemple compact en codage projet

```js
public static String exempleTernaire1(int nombre) {

    return ( (nombre >0) ? "supérieur à zéro" : "inférieur ou égale zéro");

}
```
