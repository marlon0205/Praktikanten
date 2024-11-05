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
Hier findest du Dokumentation zum Einstieg in die Java Entwicklung.

## Was ist Java?
Java ist eine Programmiersprache, die auf vielen Geräten funktioniert. Einmal schreiben, überall nutzen – das ist das Prinzip. Java wird für alles Mögliche genutzt, von Apps bis Webseiten.

<br/>

## Einfaches Hello World!
```java
public class ErstesProgramm {
	public static void main(String[] args){
		System.out.println("Hello world!");
	}
}
```

Hier sehen wir unsere erste Java-Klasse die den Namen ``ErstesProgramm`` trägt. Diese Klasse enthält die ``main-Methode``. 

``public class ErstesProgramm `` definiert unsere Klasse und muss in Jeder .java Datei stehen. Was genau public bedeutet und welche Optionen es noch gibt, werden wir später diskutieren. An der Position von ``ErstesProgramm`` muss immer der Dateiname stehen ohne die Endung.

``public static void main(String[] args)`` ist unser Ausdruck für die main-Methode. Er ist auch unser Start des Programmes, unser Programm schreiben wir zwischen die geschweiften Klammern nach unserer main-Methode. 

``System.out.println("Hello world!")`` ist unser Ausdruck um etwas in die Konsole zuschreiben.

<br/>

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

Natürlich beschränken sich unsere Datentypen nicht nur auf Ganzzahlen. 
* int : Ganzzahlen
	```java 
	int variablenName = 10;
	```
* double : Kommazahlen
	```java
	double variablenName = 12.4;
	```
* String : Zeichenkette
	```java
	String variablenName = "Hallo Welt!";
	```
* boolean : ja / nein oder true / false
	```java
	boolean variablenName = false;
	boolean variablenName = true;
	```
* char : Textzeichen
	```java
	char variablenName = 'c';
	```
	
Es gibt noch ein paar mehr Datentypen, aber für den Anfang können wir uns auf diese Beschränken. Weitere wirst du im verlaufe der Dokumentation erlernen.

## Besonderheiten
### Increments
Der Post-Inkrement-Operator ``i++`` ist besonders nützlich, wenn man den aktuellen Wert einer Variablen verwenden und sie anschließend um 1 erhöhen möchte. Er besteht aus zwei Hauptteilen: der Verwendung des aktuellen Werts und der Erhöhung der Variablen.

#### Syntax
```java
int i = 0;
System.out.println(i++); // Ausgabe: 0
System.out.println(i); // Ausgabe: 1
```

#### Funktionsweise
1. Verwendung des aktuellen Werts: Der aktuell der Variable ``i`` wird verwendet.
2. Wert der variable ``i`` wird um 1 erhöht. (gleich wie: ``i = i + 1;``)

#### Beispiel
```java
int i = 0;
System.out.println("Vor dem Inkrement: " + i); // Ausgabe: Vor dem Inkrement: 0
System.out.println("Verwendung von i++: " + i++); // Ausgabe: Verwendung von i++: 0
System.out.println("Nach dem Inkrement: " + i); // Ausgabe: Nach dem Inkrement: 1
```

