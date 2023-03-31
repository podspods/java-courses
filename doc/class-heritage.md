[< précédent](../README.md)

# Héritage

[doc ici](https://www.w3schools.com/java/java_inheritance.asp)

# superclass (class parent)

c'est la classe parent que l'on peux hériter

# subclass (class enfant)

c'est la classe enfant; la class qui herite d'un parent

# public

- Pour un attribut  
  Valeur disponible pour tout le monde en lecture et modification
  c'est une pratique à **éviter** pour les attributs.

```java
public int  buldingSize =25;
```

pour une méthode
c'est indispensable afin de rendre disponible.

```java
public String getCeoName(){
    return this.ceoName;
};
```

# private

```java
    private String  name ="brand name exemple: Adidas" ;
```

```java
    private String  name ="brand name exemple: Adidas" ;
```

# protected

```java
    protected int  chairQuantity =25;
```

# règle d'héritage

1. l'enfant herite de tout les attributs et méthodes du **public** parent
1. Si l'enfant à une méthode du même nom que son père `getName()` alors on utilise celui de l'enfant
1. si l'enfant n'a pas de méthode alors que son père l'a alors, on utilisera celui du père : `getCeoName`
1. Les enfants ont également accès au attribue protected

# tout le code

```java
class ShoeBrand{

    protected int  chairQuantity =25;
    private String  name ="brand name exemple: Adidas" ;
    private String  ceoName = "Arthur";
    private int tableQuatity= 100;


    public String getCeoName(){
        return this.ceoName;
    }
    public void setCeoName(String value){
         this.ceoName= value;
    }
    public String getName(){
        return this.name;
    }
    public void setName(String value){
         this.name= value;
    }

    public int getTableQuatity(){
        return this.tableQuatity;
    }
    public void setTableQuatity(int value){
         this.tableQuatity= value;
    }
    public int getChairQuatity(){
        return this.chairQuantity;
    }
    public void setChairQuatity(int value){
         this.chairQuantity= value;
    }


}

class ShoeModel extends ShoeBrand{

    private String model = "model name stan smith";
    private int tableQuatity= 3;

    public String getModel(){
        return this.model;
    }

    public void setModel(String value){
         this.model= value;
    }
    public int getTableQuatity(){
        return this.tableQuatity;
    }
    public void setTableQuatity(int value){
         this.tableQuatity= value;
    }

    public int getTotalTableQuatity(){
        return this.calculeTotal();
    }

    private int calculeTotal(){
        return this.tableQuatity + super.getTableQuatity();
    }

}


public class Main {

    public static void main(String[] args) {
        exempleHeritageClass();
    }
}

 public static  void exempleHeritageClass() {
        ShoeBrand myBrand = new ShoeBrand();
        System.out.printf("marque - nom init  [%s] \n",  myBrand.getName ());
        myBrand.setName ("Ma nouvelle Marque");
        System.out.printf("marque - Nom (modifé) [%s] \n",  myBrand.getName ());
        System.out.printf("marque -  CEO [%s] \n",  myBrand.getCeoName ());
        System.out.printf("marque - nb table [%d] \n",  myBrand.getTableQuatity ());
        myBrand.setTableQuatity (125);
        System.out.printf("marque - nb table [%d] \n",  myBrand.getTableQuatity ());
        System.out.printf("marque - nb chaise [%d] \n",  myBrand.getChairQuatity ());
        myBrand.setChairQuatity (myBrand.getChairQuatity()+1);
        System.out.printf("marque - nb chaise modifé dans le père [%d] \n",  myBrand.getChairQuatity ());

        ShoeModel myShoe = new ShoeModel();
        System.out.printf("model - Nom [%s] \n",  myShoe.getName ());
        System.out.printf("model - CEO [%s] \n",  myShoe.getCeoName ());
        System.out.printf("model - nb table [%d] \n",  myShoe.getTableQuatity ());
        System.out.printf("model - nb table hérité [%d] \n",  myShoe.getTotalTableQuatity());
        System.out.printf("model - nb chaise [%d] \n",  myShoe.getChairQuatity ());
        myShoe.setChairQuatity (myShoe.getChairQuatity ()*2);
        System.out.printf("model - nb chaise modifé par l'enfant [%d] \n",  myShoe.getChairQuatity ());
        System.out.printf("marque - nb chaise modifé par l'enfant [%d] \n",  myBrand.getChairQuatity ());


    }
```
