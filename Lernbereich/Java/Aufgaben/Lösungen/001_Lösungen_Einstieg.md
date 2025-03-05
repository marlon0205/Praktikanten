

<<<<<<< HEAD
### Erste Lösung: Durchschnitt Berechnen
=======
### 1. Erste Lösung: Durchschnitt Berechnen
>>>>>>> origin/main
```java
public class AverageCalculator {
    public static void main(String[] args) {
        // Deklaration und Initialisierung der Variablen
        double num1 = 5.5;
        double num2 = 10.0;
        double num3 = 7.5;

        // Berechnung des Durchschnitts
        double average = (num1 + num2 + num3) / 3;

        // Ausgabe des Ergebnisses
        System.out.println("Der Durchschnitt der Zahlen ist: " + average);
    }
}
<<<<<<< HEAD
=======
```

### 2. Zweite Lösung: Alterskategorie
```java
public class AgeCategorizer {
    public static void main(String[] args) {
        // Altersvariable deklarieren und initialisieren
        int age = 25; // Beispielwert, kann geändert werden

        // Alterskategorisierung
        if (age >= 0 && age <= 12) {
            System.out.println("Sie sind ein Kind.");
        } else if (age >= 13 && age <= 19) {
            System.out.println("Sie sind ein Teenager.");
        } else if (age >= 20 && age <= 64) {
            System.out.println("Sie sind ein Erwachsener.");
        } else if (age >= 65) {
            System.out.println("Sie sind ein Senior.");
        } else {
            System.out.println("Ungültiges Alter eingegeben.");
        }
    }
}
>>>>>>> origin/main
```