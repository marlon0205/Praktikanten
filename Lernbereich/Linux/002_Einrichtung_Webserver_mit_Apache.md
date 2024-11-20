## Was ist Apache?

Der **Apache HTTP Server**, oft einfach **Apache** genannt, ist ein **freier und plattformunabhängiger Webserver**. Er wurde 1995 von der Apache Software Foundation entwickelt und ist einer der meistgenutzten Webserver im Internet.

Apache ist **modular aufgebaut**, was bedeutet, dass er durch verschiedene Module erweitert werden kann, um zusätzliche Funktionen zu bieten. Er unterstützt viele Betriebssysteme wie Linux, Windows und macOS und kann mit verschiedenen Skriptsprachen wie PHP, Perl und Python arbeiten

Einfach gesagt, Apache ist eine Software, die Webseiten im Internet bereitstellt. Wenn du eine Webseite besuchst, sendet dein Browser eine Anfrage an den Server, auf dem die Webseite gespeichert ist. Apache empfängt diese Anfrage und liefert die entsprechenden Inhalte (wie Texte, Bilder und Videos) an deinen Browser zurück
## Schritt 1: Apache installieren

1. **Systempakete aktualisieren**:
    
    ```bash
    sudo apt update
    ```
    
2. **Apache installieren**:
    
    ```bash
    sudo apt install apache2
    ```
    

## Schritt 2: Firewall anpassen

3. **Firewall-Regeln für Apache hinzufügen**:
    
    ```bash
    sudo ufw allow 'Apache'
    ```
    
4. **Firewall-Status überprüfen**:
    
    ```bash
    sudo ufw status
    ```
    

## Schritt 3: Apache-Dienst überprüfen

5. **Apache-Dienststatus überprüfen**:
    
    ```bash
    sudo systemctl status apache2
    ```
    
    Du solltest eine Ausgabe sehen, die bestätigt, dass der Dienst läuft.

## Schritt 4: Standard-Webseite überprüfen

6. **IP-Adresse des Servers herausfinden**:
    
    ```bash
    hostname -I
    ```
    
7. **Standard-Webseite im Browser aufrufen**: Öffne deinen Browser und gib die IP-Adresse deines Servers ein (z.B. `http://deine_server_ip`). Du solltest die Standard-Apache-Webseite sehen.

## Schritt 5: Eigene Webseite einrichten

8. **Verzeichnis für deine Webseite erstellen**:
    
    ```bash
    sudo mkdir -p /var/www/deine_domain
    ```
    
9. **Berechtigungen anpassen**:
    
    ```bash
    sudo chown -R $USER:$USER /var/www/deine_domain
    sudo chmod -R 755 /var/www/deine_domain
    ```
    
10. **Beispiel-HTML-Datei erstellen**:
    
    ```bash
    nano /var/www/deine_domain/index.html
    ```
    
    Füge folgenden Inhalt hinzu oder schreibe deinen eigenen:
    
    HTML
    
    ```html
    <html>
    <head>
        <title>Willkommen bei deine_domain!</title>
    </head>
    <body>
        <h1>Erfolg! Dein Apache-Webserver funktioniert!</h1>
    </body>
    </html>
    ```
    
## Schritt 6: Virtuellen Host konfigurieren

11. **Virtuelle Host-Datei erstellen**:
    
    ```bash
    sudo nano /etc/apache2/sites-available/deine_domain.conf
    ```
    
    Füge folgenden Inhalt hinzu:
    
    ```apache
    <VirtualHost *:80>
        ServerAdmin webmaster@deine_domain
        ServerName deine_domain
        ServerAlias www.deine_domain
        DocumentRoot /var/www/deine_domain
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
    </VirtualHost>
    ```
    
12. **Virtuellen Host aktivieren**:
    
    ```bash
    sudo a2ensite deine_domain.conf
    ```
    

## Schritt 7: Standardseite deaktivieren

13. **Standardseite deaktivieren**:
    
    ```bash
    sudo a2dissite 000-default.conf
    ```
    
14. **Apache neu laden**:
    
    ```bash
    sudo systemctl reload apache2
    ```
    

## Schritt 8: Webseite testen

15. **Browser öffnen und deine Domain eingeben**: Gib `http://deine_domain` in die Adressleiste deines Browsers ein. Du solltest deine erstellte Webseite sehen.