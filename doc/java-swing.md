[< précédent](../README.md)

# Bibliothèque graphique Swing

[une doc ici](https://www.geeksforgeeks.org/introduction-to-java-swing/)

[developpez.com](https://baptiste-wicht.developpez.com/tutoriels/java/swing/debutant/)

1. Swing utilise son propre thread de traitement, qu'on appelle l'EDT (Event Dispatch Thread). C'est-à-dire que dans chaque application, on a 2 threads (au minimum), un thread pour le programme en lui-même et un thread pour Swing.
1. La règle est simple, on ne fait rien de graphique dans le thread principal et on ne fait rien d'autre que du graphique dans le thread Swing.
1. On crée donc une tâche (Runnable) contenant le code dédié à la création de la fenêtre et on l'ajoute dans le thread de Swing.

# JWindow

Fenetre basic  
spash-screen

instanciation

```java
JWindow window = new JWindow();
```

taille de la fenetre

```java
window.setSize(300, 200);
```

le rendre visible

```java
window.setVisible(true)
```

## tout le code

```java
import java.io.*;
import javax.swing.*;
public class Main {
	public static void main(String[] args) {
		SwingUtilities.invokeLater(new Runnable(){
			public void run(){
				//On crée une nouvelle instance de notre JWindow
				JWindow window = new JWindow();
				window.setSize(300, 200);//On lui donne une taille pour qu'on puisse la voir
				window.setVisible(true);//On la rend visible
			}
		});

		try {
			Thread.sleep(5000);
		} catch (InterruptedException e) {}

		System.exit(0);
	}
}
```

# JDialog

boite de dialog : peut-être modale (ou pas)

## tout le code

```java
public class TestJDialog {
	public static void main(String[] args){
		SwingUtilities.invokeLater(new Runnable(){
			public void run(){
				//On crée une nouvelle instance de notre JDialog
				JDialog dialog = new JDialog();
				dialog.setSize(300, 200);//On lui donne une taille
				dialog.setTitle("Première fenêtre"); //On lui donne un titre
				dialog.setVisible(true);//On la rend visible
				setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //On dit à l'application de se fermer lors du clic sur la croix
			}
		});
	}
}
```

# JFrame

Une Jframe est découpée en plusieurs parties :

1. la fenêtre,
1. le RootPane (principal),
1. le LayeredPane, (contient menubar et contentpane)
1. la MenuBar,
1. et le GlassPane (intercept les events).
1. le ContentPane

fenetre principal de l'application

creéation du Thread swing

```java
SwingUtilities.invokeLater(new Runnable(){
			public void run(){
```

la class fenêtre

```java
public class SimpleFenetre extends JFrame{

	public SimpleFenetre(){
		super();

		build();//On initialise notre fenêtre
	}

	private void build(){
		setTitle("Ma première fenêtre"); //On donne un titre à l'application
		setSize(320,240); //On donne une taille à notre fenêtre
		setLocationRelativeTo(null); //On centre la fenêtre sur l'écran
		setResizable(false); //On interdit la redimensionnement de la fenêtre
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //On dit à l'application de se fermer lors du clic sur la croix
	}
}
```

## tout le code

```java
public class Main extends JFrame{
	public static void main(String[] args) {

        SwingUtilities.invokeLater(new Runnable(){
			public void run(){
				//On crée une nouvelle instance de notre JDialog
		        SimpleFenetre myWindow = new SimpleFenetre();
                myWindow.setVisible(true);
			}
		});
    }


import javax.swing.JFrame;

public class SimpleFenetre extends JFrame{

	public SimpleFenetre(){
		super();

		build();//On initialise notre fenêtre
	}

	private void build(){
		setTitle("Ma première fenêtre"); //On donne un titre à l'application
		setSize(320,240); //On donne une taille à notre fenêtre
		setLocationRelativeTo(null); //On centre la fenêtre sur l'écran
		setResizable(false); //On interdit la redimensionnement de la fenêtre
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //On dit à l'application de se fermer lors du clic sur la croix
	}
}

```

# placement des composants

## Le positionnement absolu

## L'utilisation d'un gestionnaire de placement (layout)

1. FlowLayout (par défaut)
1. CardLayout
1. GridLayout
1. GridBagLayout

# bouton

# checkbox

1. Translucent and shaped Window in Java
1. ScrollPaneLayout Class
1. Java Swing - JPanel With Examples
1. Internal Frame with examples
1. JMenuBar
1. JFileChooser
1. Look and Feel
1. JTextField
1. JProgressBar
1. PasswordField

# action listener
