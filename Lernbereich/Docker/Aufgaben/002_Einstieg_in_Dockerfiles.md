# Dockerfile Aufgaben

Bei den nachfolgenden Aufgaben geht es darum ein Docker Image zu definieren. Welches dann von den Entwicklern für die Entwicklung von
C Applikationen verwendet werden kann.

1. Erstelle eine Datei mit dem Namen `Dockerfile`.
1. Die Dockerfile soll `Debian 12.5` als Baseimage verwenden.
1. Setze den Vendor auf `NORMRISK Develop @FIRMANAME`
1. Es sollen die neuesten Updates installiert sein
1. Folgende Applikationen sollen vorinstalliert werden
    - wget 
    - make 
    - vim 
    - gcc 
    - maven 
    - Openjdk 21 headless
    - xz-utils
    - gdb 
1. Der Benutzer soll den Namen `nrdev` tragen.
1. Das Passwort des Nutzers soll `nrdev` sein.
1. `nrdev` soll sudoer sein.
1. Es wird eine Gruppe `firebird` benötigt.
1. `nrdev`soll Teil der Gruppe sein.
1. Erstelle folgende Verzeichnisse im Benutzerverzeichniss des `nrdev` Nutzers.
    ```
    home 
    |--> normrisk-source
    |--> normrisk-jni-source
    |--> normrisk-runtime
    ```
1. Diese Verzeichnisse sollen auch auf dem Hostsystem erstellt werden, mit einigen Beispieldateien. Diese Dateien können beliebigen Inhalt haben. Wichtig ist das diese Verzeichnisse auf dem HOST erstellt werden, NICHT in dem Docker Container.
    ```
    home 
    |--> normrisk-source
        |--> main.c
        |--> mylib.c
        |--> mysecondlib.c
    |--> normrisk-jni-source
        |--> my-jni-main.java
        |--> my-jni-main.c
    |--> normrisk-runtime
        |--> my-app.c
    ```
1. Binde diese drei Verzeichnisse beim Start des Docker Containers per Argument in die entsprechenden drei leeren Verzeichnisse innerhalb des Docker Containers ein.
