[< précédent](../README.md)

# type HashMap

[DOc HashMap](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/HashMap.html)

Le HashMap est un autre ensemble adapté à
d’autres situation très différentes  
Celui-ci n’est pas ordonné et fonctionne avec des
couples `clef et valeur`.

**Important :**  
Attention cependant, HashMap demande des types
sous forme d’objets. voir tableau de correspondance ci dessous.

| Type primitif | Objet     |
| ------------- | --------- |
| int           | Integer   |
| double        | Double    |
| char          | Character |
| bool          | Boolean   |
| byte          | Byte      |
| long          | Long      |

# import

```java
import java.utils.HashMap
```

# Creation

```java
HashMap <Character,Integer> statHashMap = new HashMap <Character,Integer> ();
```

# Update

```java
  statHashMap.put(myChar,0);
```

# RetreiveUpdate

```java
  statHashMap.get(key)
```

# Delete

supprime tous les valeurs

```java
  statHashMap.clear();
```

supprime tous les valeurs

```java
  statHashMap.remove(key);
```

# fonctions utiles

| Méthode       | Description                     |
| ------------- | ------------------------------- |
| put           | Ajoute ou modifie une valeur    |
| get           | Lit une valeur                  |
| remove        | Supprime une valeur et sa clef  |
| clear         | Supprime toutes les données     |
| containsValue | Recherche une valeur spécifique |

# voir exercice bandit-manchot
