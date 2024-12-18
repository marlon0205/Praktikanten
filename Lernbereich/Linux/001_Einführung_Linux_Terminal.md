# Einführung in die Linux-Shell
## Was ist die Linux-Shell?
Die Linux-Shell ist eine Schnittstelle, die es dir ermöglicht, mit dem Betriebssystem zu kommunizieren. Sie nimmt Befehle entgegen, führt sie aus und gibt die Ergebnisse zurück. Die am häufigsten verwendete Shell ist die Bash (Bourne Again Shell).


## Grundlegende Befehle

### 1. Navigieren im Dateisystem

- **pwd**: Zeigt das aktuelle Verzeichnis an
    
    ```bash
    pwd
    ```
    
    
    
- **ls**: Listet die Dateien und Verzeichnisse im aktuellen Verzeichnis auf.
    
    ```bash
    ls
    ```
    
    
    
- **cd**: Wechselt das Verzeichnis
    
    ```bash
    cd /pfad/zum/verzeichnis
    ```
    
    
    


### 2. Dateien und Verzeichnisse verwalten

- **mkdir**: Erstellt ein neues Verzeichnis
    
    ```bash
    mkdir neuer_ordner
    ```
    
    
    
- **touch**: Erstellt eine neue Datei
    
    ```bash
    touch neue_datei.txt
    ```
    
    
    
- **rm**: Löscht eine Datei
    
    ```bash
    rm datei.txt
    ```
    
    
    
- **rmdir**: Löscht ein leeres Verzeichnis
    
    ```bash
    rmdir leerer_ordner
    ```
    
    
    


### 3. Dateiinhalte anzeigen

- **cat**: Zeigt den Inhalt einer Datei an
    
    ```bash
    cat datei.txt
    ```
    
    
    
- **less**: Zeigt den Inhalt einer Datei seitenweise an
    
    ```bash
    less datei.txt
    ```
    
    
    
- **head**: Zeigt die ersten Zeilen einer Datei an
    
    ```bash
    head datei.txt
    ```
    
    
    
- **tail**: Zeigt die letzten Zeilen einer Datei an
    
    ```bash
    tail datei.txt
    ```
    

## Praktische Übungen

1. Erstelle ein Verzeichnis namens projekt und wechsle in dieses Verzeichnis
2. Erstelle in diesem Verzeichnis drei neue Dateien: datei1.txt, datei2.txt und datei3.txt
3. Liste die Dateien im Verzeichnis auf und überprüfe, ob sie erstellt wurden
4. Schreibe in jede Datei einen kurzen Text
5. Zeige den Inhalt jeder Datei an



**Nützliche Links:**
- [Befehlsübersicht Linux Shell](https://wiki.ubuntuusers.de/Shell/Befehls%C3%BCbersicht/)
- [Terminal Farben verstehen](https://www.crstin.com/de/terminal-colors/)
- [Vim Cheat Sheet](https://vim.rtorr.com/lang/de_de)
