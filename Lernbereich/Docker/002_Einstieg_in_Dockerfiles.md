# Einstieg in Dockerfiles

Dockerfiles verwendet man um eigene "Docker Umgebungen" aufzubauen. In einer Dockerfile kann man die verwendete Distribution, die zu installierenden Applikationen und verfügbaren Benutzer sowie Berechtigungsgruppen vordefinieren.
Dadurch erhällt man eine Umgebung die immer gleich ist und mit Kollegen geteilt oder in einer Repository versioniert werden kann.

Eine Dockerfile ist eine Textdatei ohne Suffix die meist `Dockerfile` genannt wird. Man kann diese auch anders benennen wenn man möchte.

Diese Datei kennt mehrere [Instruktionen](https://docs.docker.com/reference/dockerfile/). 

Die einfaschste Dockerfile ist 
```Dockerfile
FROM <distribution:tag>

```
Diese gibt eine zu verwendende Distribution und deren Version an.

### Bauen einer Dockerfile
Jede `Dockerfile` muss erstmal zu einem `Docker Image` gebaut werden. Dabei führt Docker die in der `Dockerfile` definierten Instruktionen aus und verpackt das Ergebnis in einer Datei die gestartet oder mit anderen geteilt werden kann.  

Die oben gezeigte Dockerfile kann mit einem der folgenden Befehle gebaut werden
Baut die Datei in dem aktuellen Verzeichnisse die den Namen Dockerfile trägt.
```
    docker build 
```
Baut die Datei die mit dem Argument '-f' oder '-file' angegeben wird.
```
    docker build -f ./path/to/dockerfile 
```
Baut die Datei die mit dem Argument '-f' oder '-file' angegeben wird. Verwendet dabei 'buildx' das erweiterte Baumöglichkeiten mitbringt.
```
    docker buildx build -f ./path/to/dockerfile 
```

Wenn das Bauen der Dockerfile zu einem Image erfolgreich verlaufen ist kann dieses Image [gestartet](./001_Einstieg_in_Docker.md) werden.

### Die `RUN` Instruktion

Die `RUN` Instruktion wird verwendet um Kommandozeilenbefehle beim Bauen des Containers auszuführen `RUN <linux befehl> <n Argumente>`.
Beispiele sind:
```Dockerfile
FROM <distribution:tag>

RUN apt-get -y -qq install vim
RUN mkdir ./hallo/test
RUN touch text.txt
RUN touch ./hallo/test/text.txt
```

Diese Dockerfile würde beim Bauen die Applikation `VIM` installieren. Danach das Verzeichniss `./hallo/test` erstellen und zwei `.txt` Dateien erstellen. Eine im aktuellen Verzeichnis und eine im `./hallo/test`.

### Die `ENV`Instruktion

Die Instruktion wird verwendet um Umgebungsvariablen zu definieren. `ENV <Name der Variable>=<Wert der Variable>`

Beispiel:
```dockerfile
FROM <distribution:tag>

RUN apt-get -y -qq install vim

ENV SRC_DIR=./development/sourcecode
```
