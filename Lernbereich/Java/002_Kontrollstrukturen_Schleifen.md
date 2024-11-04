## Kontrollstrukturen
Kontrollstrukturen ermöglichen es, den Ablauf eines Programms zu steuern. 
Dazu gehören bedingte Anweisungen und Schleifen

## Bedingte Anweisung
```java
int zahlen = 10;
if (zahl > 5) {
	System.out.println("Zahl ist größer als 5");
} else {
	System.out.println("Zahl ist 5 oder kleiner");
}
```

Eine If-Abfrage in Java wird verwendet, um bedingte Anweisungen auszuführen. Sie überprüft, ob eine bestimmte Bedingung wahr (`true`) ist, und führt dann den entsprechenden Codeblock aus.
Sollte die Bedingung ``false`` sein, sowie wird der der Code im ``else``-Block. 

## Schleifen
Es gibt verschiedene Arten von Schleifen, welche für verschiedene Anwendungszwecke gut sind. 

### while(``Abbruch-Bedingung``)
Die while-Schleife führt den Programmcode im Schleifenkörper solange aus bis die ``Abbruch-Bedingung`` nicht mehr wahr ist. Sollte die Bedingung von Anfang an nicht wahr sein, sowie die Schleife gar nicht erst ausgeführt. Damit du das besser verstehst, gebe ich dir hier ein Beispiel:
```java
int i = 0;
while (i < 5) {
	//Schleifenkörper
    System.out.println("i ist: " + i);
    i++;
}
```
Unsere Schleife wird solange ausgeführt wie ``i < 5`` ist. In diesem Fall wird 0 bis 4 ausgegeben. Sobald ``i`` den Wert 5 erreicht, ist die Bedingung nicht mehr wahr und die Schleife endet.

### do {} while(``Abbruch-Bedingung``)
Die ``do-while`` Schleife ähnelt der ``while``-Schleife, führt den Schleifenkörper jedoch mindestens einmal aus, bevor die Bedingung überprüft wird.
```java
int i = 0;
do {
	//Schleifenkörper
    System.out.println("i ist: " + i);
    i++;
} while (i < 5);
```
In diesem Beispiel wird der Code im Schleifenkörper mindestens einmal ausgeführt, auch wenn die Bedingung von Anfang an ``false`` wäre.

### For-Schleife
Die ``for``-Schleife ist besonders nützlich, wenn die Anzahl der Durchläufe im Voraus bekannt ist. Sie besteht aus 3 Hauptteilen. Die Initialisierung, die Bedingung, die Aktualisierung. 

```java
for (int i = 0; i < 5; i++) {
    System.out.println("i ist: " + i);
}
```
