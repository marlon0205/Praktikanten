# Willkommen zu deinem Linux-Sicherheits-Guide!

## Übersicht

Dieses Repository bietet einfache Anleitungen zur Einrichtung von Firewalls und zur Verwaltung von Benutzern und Berechtigungen. Es ist speziell für Praktikanten konzipiert, die ihre Kenntnisse in der Linux-Sicherheit erweitern möchten.

## Inhaltsverzeichnis

1. Einführung in die Linux-Sicherheit
2. Einrichtung von Firewalls
    - UFW (Uncomplicated Firewall)
    - iptables
3. Benutzer- und Rechteverwaltung
    - Benutzerverwaltung
    - Rechteverwaltung
4. Nützliche Ressourcen

## Einführung in die Linux-Sicherheit

Linux-Sicherheit umfasst verschiedene Maßnahmen, um das System vor unbefugtem Zugriff und Angriffen zu schützen. Dazu gehören die Konfiguration von Firewalls, die Verwaltung von Benutzern und Berechtigungen sowie die regelmäßige Aktualisierung des Systems.

## Einrichtung von Firewalls

### UFW (Uncomplicated Firewall)

UFW ist ein benutzerfreundliches Frontend für iptables, das die Verwaltung von Firewall-Regeln vereinfacht.

1. **UFW installieren**:
    
    ```bash
    sudo apt install ufw
    ```
    
2. **UFW aktivieren**:
    
    ```bash
    sudo ufw enable
    ```
    
3. **Standardregeln festlegen**:
    
    ```bash
    sudo ufw default deny incoming
    sudo ufw default allow outgoing
    ```
    
4. **Regeln hinzufügen**:
    - SSH-Verbindungen erlauben:
        
        ```bash
        sudo ufw allow ssh
        ```
        
    - HTTP und HTTPS erlauben:
        
        ```bash
        sudo ufw allow http
        sudo ufw allow https
        ```
        
5. **Firewall-Status überprüfen**:
    
    ```bash
    sudo ufw status
    ```
    

### iptables

iptables ist ein leistungsstarkes Werkzeug zur Konfiguration von Firewall-Regeln auf niedriger Ebene.

1. **Aktuelle Regeln anzeigen**:
    
    ```bash
    sudo iptables -L
    ```
    
2. **Eingehenden Traffic blockieren, außer SSH**:
    
    ```bash
    sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
    sudo iptables -A INPUT -j DROP
    ```
    
3. **Regeln speichern**:
    
    ```bash
    sudo sh -c "iptables-save > /etc/iptables/rules.v4"
    ```
    

## Benutzer- und Rechteverwaltung

### Benutzerverwaltung

1. **Neuen Benutzer erstellen**:
    
    ```bash
    sudo adduser neuer_benutzername
    ```
    
2. **Benutzer zu einer Gruppe hinzufügen**:
    
    ```bash
    sudo usermod -aG gruppe neuer_benutzername
    ```
    
3. **Benutzer löschen**:
    
    ```bash
    sudo deluser benutzername
    ```
    

### Rechteverwaltung

1. **Dateiberechtigungen anzeigen**:
    
    ```bash
    ls -l dateiname
    ```
    
2. **Dateiberechtigungen ändern**:
    - Leserechte für alle hinzufügen:
        
        ```bash
        sudo chmod a+r dateiname
        ```
        
    - Schreibrechte für den Besitzer hinzufügen:
        
        ```bash
        sudo chmod u+w dateiname
        ```
        
3. **Besitzer einer Datei ändern**:
    
    ```bash
    sudo chown neuer_besitzer dateiname
    ```
    

## Nützliche Ressourcen