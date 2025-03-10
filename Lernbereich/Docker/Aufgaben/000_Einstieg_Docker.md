# Schritt für Schritt einführung in Docker

1. Was ist Docker?
    - Lese dich im Internet in Docker ein. 
    - Überlege dir wofür man es Verwendet. 

1. Installation 
    - Stelle sicher das Docker auf deinem Rechner installiert ist. Bitte wenn nötig Client Management darum dir Docker zu installieren. 
    - Stelle sicher das Docker gestartet wurde.

1. Erste Docker-Befehle ausprobieren
    - Ziel: Die grundlegenden Docker-Befehle kennenlernen und erste Erfahrungen sammeln.
    - Schritte:
        - Docker-Informationen abrufen:
            Öffne das Terminal oder die Eingabeaufforderung.
            Gib den Befehl `docker info` ein und drücke Enter. Dieser Befehl gibt dir eine Übersicht über deine Docker-Installation, einschließlich der Version, Anzahl der laufenden Container, Images und weiterer nützlicher Informationen.
        - Vorhandene Docker-Images anzeigen:
            Tippe `docker images` ein und drücke Enter. Dieser Befehl zeigt dir eine Liste der Docker-Images, die auf deinem Computer gespeichert sind. Ein Image ist eine Vorlage, aus der Docker Container erstellt.
            Wenn du Docker gerade erst installiert hast, wird die Liste wahrscheinlich leer sein.
        - Laufende Container anzeigen:
            Gib `docker ps` ein und drücke Enter. Dieser Befehl zeigt dir alle Container, die derzeit auf deinem Computer laufen.
            Wenn du bisher noch keinen Container gestartet hast, wird die Liste leer sein. Du wirst in den nächsten Aufgaben lernen, wie du Container startest.

1. Einen einfachen "Hello World"-Container starten
    - Ziel: Deinen ersten Docker-Container starten und die Funktionsweise von Docker in Aktion sehen.
    - Schritte:
        - Einen "Hello World"-Container starten:
            - Im Terminal gibst du `docker run dockerhub.registry.domain.de/hello-world` ein und drückst Enter.
            - Docker wird ein spezielles „hello-world“-Image aus dem Internet herunterladen, wenn es nicht bereits auf deinem Computer vorhanden ist.
            - Nachdem das Image heruntergeladen wurde, startet Docker einen Container basierend auf diesem Image. Der Container führt ein kleines Programm aus, das „Hello from Docker!“ ausgibt und dann beendet wird.
        - Ergebnis ansehen:
            - Schau dir die Ausgabe im Terminal an. Du solltest eine Nachricht sehen, die erklärt, dass Docker erfolgreich funktioniert hat. Diese einfache Ausgabe zeigt dir, dass Docker Container schnell starten kann, um Programme auszuführen.

1. Erste Docker-Befehle erneut ausführen. Diese Aufgabe wird absichtlich widerholt um die Nutzung der Befehle zu verdeutlichen.
    - Ziel: Die grundlegenden Docker-Befehle kennenlernen und erste Erfahrungen sammeln.
    - Schritte:
        - Docker-Informationen abrufen:
            Öffne das Terminal oder die Eingabeaufforderung.
            Gib den Befehl `docker info` ein und drücke Enter. Was macht dieser Befehl?  Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?
        - Vorhandene Docker-Images anzeigen:
            Tippe `docker images` ein und drücke Enter. Was macht dieser Befehl? Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?
        - Laufende Container anzeigen:
            Gib `docker ps` ein und drücke Enter. Was macht dieser Befehl? Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?

1. Ein eigenes Docker-Image erstellen
    - Ziel: Ein einfaches Dockerfile erstellen, um ein eigenes Docker-Image zu bauen und einen Container daraus zu starten.
    - Schritte:
        - Einen neuen Projektordner erstellen:
            - Auf deinem Computer erstellst du einen neuen Ordner für dein Projekt. Du kannst ihn z. B. `mein_erstes_dockerprojekt` nennen. - Dieser Ordner wird alle Dateien für dein Docker-Projekt enthalten.
        - Dockerfile erstellen:
            - In deinem neuen Ordner erstellst du eine Datei mit dem Namen `Dockerfile` (ohne Dateiendung).
            - Öffne die Datei in einem Texteditor (z.B. Notepad, Visual Studio Code).
            - Füge folgenden Inhalt in die Datei ein:  

            ```Dockerfile

            FROM dockerhub.registry.domain.de/alpine
            CMD ["echo", "Hallo Docker!"]

            ```

            Diese einfachen Zeilen sagen Docker, dass es ein Image basierend auf „Alpine Linux“ (eine sehr schlanke Linux-Distribution) erstellen soll. Wenn der Container gestartet wird, gibt er „Hallo Docker!“ im Terminal aus.
        - Docker-Image bauen:
            - Öffne das Terminal und wechsle in den Ordner, den du gerade erstellt hast. Das machst du, indem du `cd pfad/zum/ordner` eingibst (ersetze „pfad/zum/ordner“ durch den tatsächlichen Pfad zu deinem Ordner).
            - Gib dann `docker build -t mein_docker_image .` ein und drücke Enter. Docker wird das Image basierend auf deinem Dockerfile erstellen. Der `-t` Schalter gibt dem Image einen Namen, in diesem Fall `mein_docker_image`.
        - Container aus deinem Image starten:
            - Starte den Container, indem du `docker run mein_docker_image` eingibst. Im Terminal sollte „Hallo Docker!“ erscheinen. Das bedeutet, dass dein Container erfolgreich läuft und dein eigenes Image verwendet.

1. Erste Docker-Befehle erneut ausführen. Diese Aufgabe wird absichtlich widerholt um die Nutzung der Befehle zu verdeutlichen.
    - Ziel: Die grundlegenden Docker-Befehle kennenlernen und erste Erfahrungen sammeln.
    - Schritte:
        - Docker-Informationen abrufen:
            Öffne das Terminal oder die Eingabeaufforderung.
            Gib den Befehl `docker info` ein und drücke Enter. Was macht dieser Befehl?  Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?
        - Vorhandene Docker-Images anzeigen:
            Tippe `docker images` ein und drücke Enter. Was macht dieser Befehl? Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?
        - Laufende Container anzeigen:
            Gib `docker ps` ein und drücke Enter. Was macht dieser Befehl? Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?

1. Einen Webserver mit Docker starten
    - Ziel: Einen Webserver in einem Docker-Container laufen lassen und über den Browser darauf zugreifen.
    - Schritte:
        - Nginx-Webserver starten:
            - Gib im Terminal folgenden Befehl ein:

            ```bash

            docker run --name mein_webserver -d -p 8080:80 dockerhub.registry.domain.de/nginx

            ```
            Dieser Befehl startet einen Container mit Nginx, einem sehr beliebten Webserver. Der `-name` Schalter gibt dem Container den Namen `mein_webserver`. Der `-d` Schalter sorgt dafür, dass der Container im Hintergrund läuft (detached mode), und `-p 8080:80` weist Docker an, den internen Port 80 des Containers auf Port 8080 deines Computers zu mappen.
        - Webserver im Browser anzeigen:
            - Öffne deinen Webbrowser und gehe zu `http://localhost:8080`. Du solltest die Nginx-Willkommensseite sehen, was bedeutet, dass der Webserver erfolgreich läuft und über Docker betrieben wird.
        - Webserver stoppen:
            - Wenn du den Webserver stoppen möchtest, gib einfach `docker stop mein_webserver` ein. Der Container wird angehalten, aber er bleibt auf deinem System gespeichert, falls du ihn später wieder starten möchtest.

1. Erste Docker-Befehle erneut ausführen. Diese Aufgabe wird absichtlich widerholt um die Nutzung der Befehle zu verdeutlichen.
    - Ziel: Die grundlegenden Docker-Befehle kennenlernen und erste Erfahrungen sammeln.
    - Schritte:
        - Docker-Informationen abrufen:
            Öffne das Terminal oder die Eingabeaufforderung.
            Gib den Befehl `docker info` ein und drücke Enter. Was macht dieser Befehl?  Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?
        - Vorhandene Docker-Images anzeigen:
            Tippe `docker images` ein und drücke Enter. Was macht dieser Befehl? Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?
        - Laufende Container anzeigen:
            Gib `docker ps` ein und drücke Enter. Was macht dieser Befehl? Hat sich die Ausgabe im Vergleich zu dem letzten Mal als du den Befehl ausgeführt hast verändert? Wenn ja, wie und warum?

1. Container verwalten
    - Ziel: Lernen, wie man Container in Docker verwaltet, einschließlich Anzeigen, Stoppen und Löschen.
    - Schritte:
        - Alle Container anzeigen:
            - Um eine Liste aller Container zu sehen, die jemals auf deinem System gestartet wurden (auch die gestoppten), gib `docker ps -a` ein.
            - Diese Liste zeigt die Container-ID, den Namen, den Status und weitere Informationen an. Container, die gerade nicht laufen, haben den Status „Exited“.
        - Einen gestoppten Container löschen:
            - Wenn du einen Container nicht mehr benötigst, kannst du ihn löschen. Dafür gibst du `docker rm [CONTAINER_ID]` ein, wobei du [CONTAINER_ID] durch die ID des Containers ersetzt, den du entfernen möchtest. Die ID findest du in der Liste, die `docker ps -a` ausgibt.
            - Lösche ein Docker-Container.
        - Ein Docker-Image löschen:
            - Wenn du ein Docker-Image nicht mehr benötigst, kannst du es mit dem Befehl `docker rmi [IMAGE_ID]` löschen. Ersetze [IMAGE_ID] durch die ID oder den Namen des Images, das du entfernen möchtest. Dies hilft, Speicherplatz auf deinem Computer freizugeben`
            - Lösche ein Docker-Image.
