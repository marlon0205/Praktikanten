# Einstieg in Docker

In diesem Dokument werden wir uns mit den Grundlagen von Docker beschäftigen.

### Herunterladen eines Docker-Images aus dem Docker Hub:
Der erste Schritt ist meistens das Herunterladen von einem `Image` aus dem `Docker Hub`

```sh
docker pull <image-name>
```
Wichtig ist, den genauen Namen und Tag des Images zu kennen.
- Beispiel: `docker pull ubuntu:latest`.
Der Tag 'latest' bedeuted in dem Fall das die neueste Version heruntergeladenen wird.
Es kann empfehlenswert sein sich auf eine bestimmte Version festzulegen zb `docker pull ubuntu:17.5`. 
Dies kann die Sicherheit erhöhen da man nicht automatisch die neueste Version zieht.

### Erstellen eines Containers aus einem heruntergeladenen Image:
Nach dem Herunterladen eines Images muss dieses in einem sogenannten `Container` gestartet werden. 

```sh 
docker run -d -e <CONTAINER-ENV-Key:CONTAINER-ENV-Value> --name <container-name> <image-name:tag>
```
- Startet den Container im Hintergrund (`-d` für detached).
- Umgebungsvariablen (`-e`) anpassen.
- Container-Name (`--name`) für einfache Identifikation und Verwaltung.

In dem nachfolgenden Beispiel wird ein Container mit dem Namen `mein_container` gestartet der auf dem Image `ubuntu:latest`. 
```sh
docker run -d --name mein_container ubuntu:latest
a45a294d8ab642ad9d0ffd8b3418a4f27f85da47458e4b75a07ae33b27682262
```
Der Befehl gibt bei erfolgreichem Ausführen ein Hash zurück der den Container identifiziert.

Oft muss man den Container im `interaktiven` Modus starten
```sh
docker run -it  <CONTAINER-ENV-Key:CONTAINER-ENV-Value> --name <container-name> <image-name:tag> bash
```

Dies sorgt dafür das man direkt beim start mit dem Container interagieren kann. 
Die Konsole wechelt dann direkt in die Containerumgebung.

### Anzeigen laufender Container:
```sh
> docker ps 
```

### Anzeigen aller Container:
```sh
> docker ps -a
```
    
### Löschen eines Containers:
```sh
docker rm <container-name>
```
- Entfernt den angegebenen Container.
- Muss gestoppt sein (`docker stop <container-name>`).
    
### Anzeigen aller Docker-Images:
```sh
docker images
```
- Zeigt alle verfügbaren Docker-Images.
- Nützlich zur Überprüfung der verfügbaren Images und ihres Speicherplatzes.

### Erstellen eines Containers mit Portmapping:
Hin und wieder muss man den Port des Containers auf ein Port des Hostsystems mappen um den Zugriff auf Netzwerkresourcen innerhalb de Containers freizugeben.
```sh
docker run -d -p <HostPort>:<ContainerPort> --name <container-name> <image-name>
```

### Mounten eines Hostverzeichnisses
```sh
docker run --mount type=bind,src=<host-dir>,dst=<container-dir> 
```