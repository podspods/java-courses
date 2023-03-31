[< précédent](../README.md)

# Swing step by step

[Doc developez.com](https://baptiste-wicht.developpez.com/tutoriels/java/swing/debutant/)

# Sommaire

1. [Introduction](#introduction)

   1. [Notre projet](#notre-projet)

1. [Swing](#swing)
1. [Les fenêtres](#les-fenêtres)

1. [JWindow](#jwindow)
1. [JDialog](#jdialog)
1. [JFrame](#jframe)
1. [Application au projet](#application-au-projet)

1. [Afficher du texte dans la fenêtre](#afficher-du-texte-dans-la-fenêtre)

   1. Le positionnement des composants
   1. Afficher du texte avec un JLabel
   1. Application au projet

1. [Ajouter des boutons dans la fenêtre](#ajouter-des-boutons-dans-la-fenêtre)

   1. Attribuer une action à un bouton
      1. ActionListener
      1. AbstractAction
   1. Application au projet

1. [Demander du texte à l'utilisateur](#demander-du-texte-à-lutilisateur)

1. Utilisation d'un JTextField
1. Application au projet

1. Proposer une liste de choix à l'utilisateur

   1. Deux manières d'utiliser JComboBox
      1. Méthodes de JComboBox
      1. Création d'un modèle de liste
   1. Application au projet

1. Utiliser des boîtes de dialogue avec JOptionPane
1. Ajouter une barre de menu à votre fenêtre
1. Conclusion

   1. Remerciements
   1. Les sources

1. annexe
   1. Centrer une JFrame avec plusieurs écrans

<hr>
<hr>

# Introduction

Méga important à bien comprendre :

Swing utilise son propre thread de traitement, qu'on appelle l'EDT (Event Dispatch Thread).

Par conséquent : on a 2 threads (au minimum), un thread pour le programme (standard) et un thread pour Swing.

le thread principal (classique)
une tâche (Runnable) contenant le code dédié à la création de la fenêtre et on l'ajoute dans le thread de Swing.

## création d'un thread

```java
wingUtilities.invokeLater(new Runnable(){
			public void run(){

                ..... code  graphique ici ..
			}
		});
```

La partie graphique peut être :

- Jwindow
- JFrame
- JDialog

## Notre projet

# Swing

# Les fenêtres

## JWindow

Fenetre basic utilisé pour spash-screen

instanciation

```java
JWindow window = new JWindow();
```

## JDialog

## JFrame

## Application au projet

# Afficher du texte dans la fenêtre

## Le positionnement des composants

## Afficher du texte avec un JLabel

## Application au projet

# Ajouter des boutons dans la fenêtre

## Attribuer une action à un bouton

### ActionListener

il faut `implements ActionListener` pour utiliser les listener

```java
public class FenetreBoutonsListener extends JFrame implements ActionListener{
```

### AbstractAction

## Application au projet

# Demander du texte à l'utilisateur

## Utilisation d'un JTextField

## Application au projet

# Proposer une liste de choix à l'utilisateur

## Deux manières d'utiliser JComboBox

### Méthodes de JComboBox

### Création d'un modèle de liste

## Application au projet

# Utiliser des boîtes de dialogue avec JOptionPane

# Ajouter une barre de menu à votre fenêtre

# Conclusion

## Remerciements

## Les sources

# annexe

## Centrer une JFrame avec plusieurs écrans
