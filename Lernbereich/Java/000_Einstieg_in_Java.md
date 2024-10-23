---
tags:
  - java
  - tutorial
  - erklärung
  - einführung
aliases:
  - 000EIJ
---
## Einstieg in die Java Entwicklung
Hier erkläre ich so gut es geht, wie die Java Entwicklung funktioniert.
Verbesserungsvorschläge sind gerne gesehen :)

## Was ist Java?
Java ist eine Programmiersprache, die auf vielen Geräten funktioniert. Einmal schreiben, überall nutzen – das ist das Prinzip. Java wird für alles Mögliche genutzt, von Apps bis Webseiten.

## Einfaches Hello World!
```java
public class ErstesProgramm {
	public static void main(String[] args){
		System.out.println("Hello world!");
	}
}
```

Hier sehen wir unsere erste Java-Klasse die den Namen ``ErstesProgramm`` trägt. Diese Klasse enthält die ``main-Methode``. 
``public static void main(String[] args)`` ist unser Ausdruck für die main-Methode. Er ist auch unser Start des Programmes, unser Programm schreiben wir zwischen die geschweiften Klammern nach unserer main-Methode. 

``System.out.println("Hello world!")`` ist unser Ausdruck um etwas in die Konsole zuschreiben.

## Variablen und Datentypen
Variablen kannst du dir wie Behälter vorstellen, in denen Daten gespeichert werden können. Man kann sich also Variablen wie Boxen vorstellen, die verschiedene Arten von Informationen enthalten. 

Um eine Variable zu verwenden, muss man sie zuerst deklarieren und dann initialisieren.

#### Deklaration:
```Java
int zahl; // Deklariert eine Variable vom Typ int namens zahl
```
#### Initialisierung:
```Java
zahl = 10; // Weist der Variable zahl den Wert 10 zu
```
#### Deklaration + Initialisierung
```Java
int zahl = 10; // Deklariert und initialisiert zahl in einem Schritt
```
