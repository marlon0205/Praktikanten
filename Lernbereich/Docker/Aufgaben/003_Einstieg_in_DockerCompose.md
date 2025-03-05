# Einstieg in Docker Compose

In dieser Aufgabe soll man eine Docker Compose erstellen die zwei Dienste bereitstellt.
Einen SQL Server und eine Administrationsoberfläche für diesen Server.

## PostgreSQL Service
1. Lese dich in den [PostgreSQL](https://www.postgresql.org/) ein. Was macht der? Wozu könntest du den Verwenden?
1. Erstelle eine Docker Compose Datei die folgenden Service einbindet:
- [postgreSQL](https://hub.docker.com/_/postgres)
1. Konfiguriere den Container mit einem Default Password und Benutzer
1. Konfiguriere eine Default Datenbank
1. Definiere die Ports von denen der Container erreichbar sein soll.
1. Konfiguriere ein Volume für den Container so das die Datenbankend ie im PostgreSQL angelegt werden auf der Host Maschine persistiert werden.
1. Verwende den DBeaver um dich auf die Datenbank aufzuschalten. Erstelle eine Tabelle Benutzer(Id[int]:PK, Name[String], Nachname[String], Alter[Int]) und Inserte ein Paar Zeilen.

## PGAdmin Service
1. Lese dich in den PG Admin ein. Was macht der? Wozu könntest du den Verwenden?
1. Installiere dir den [PGAdmin](https://www.pgadmin.org/) falls nicht schon passiert.
1. Verbinde dich mit der von dir erstellten PostgeSQL Instanz 
1. Lege eine Datenbank an mit Tabelle und Testdaten deiner Wahl
1. Füge der Compose folgenden Service hinzu
- [pgAdmin](https://www.pgadmin.org/download/pgadmin-4-container/)

## Netzwerk
1. Konfiguriere ein Netzwerk für beide Container innerhalb der Compose Datei so das beide miteinander kommunizieren können.

## Verbindung zwischen PGAdmin und PostgreSQL

1. Logge dich auf der Web Konsole des PGAdmins an.
1. Trage deine PostgreSQL Datenbank in den PGAdmin ein.
1. Prüfe ob du deine Datenbank sehen kannst

## Konfiguration auslagern
1. Lagere die Zugangsdaten in je eine Konfigurationsdatei aus.

# Fortgeschrittene Docker Compose Aufgaben

## Datenbank-Sicherung und Wiederherstellung

1. Automatisierte Backups:  
    Recherchiere, wie man regelmäßige Backups von PostgreSQL-Datenbanken einrichtet.
    Ergänze deine Docker Compose Datei um einen neuen Service, der regelmäßig ein Backup der Datenbank durchführt.
    Stelle sicher, dass die Backups auf dem Host-System gespeichert werden.

1. Wiederherstellung:  
    Erstelle ein Skript, das die Wiederherstellung der Datenbank aus einem Backup ermöglicht.
    Teste die Wiederherstellung, indem du einen neuen PostgreSQL-Container startest und die Daten aus einem Backup einspielst.

## Monitoring und Logging

1. Überwachung der Datenbank:  
    Recherchiere, welche Tools zur Überwachung von PostgreSQL geeignet sind (z.B. Prometheus, Grafana).
    Integriere ein Monitoring-Tool in deine Docker Compose Datei, um die Performance und den Zustand der PostgreSQL-Datenbank zu überwachen.

1. Logging:  
    Konfiguriere den PostgreSQL-Container so, dass Logs auf dem Host-System gespeichert werden.
    Verwende ein Logging-Tool wie ELK Stack (Elasticsearch, Logstash, Kibana) oder Loki, um die Logs zu sammeln und zu analysieren.

## Skalierung und Load Balancing

1. Datenbank-Replikation:  
    Lese dich in die PostgreSQL-Replikation ein.
    Erstelle eine Docker Compose Datei, die einen Master- und einen oder mehrere Slave-Datenbankserver konfiguriert.
    Teste die Replikation, indem du Daten in den Master-Server einfügst und prüfst, ob diese auf den Slave-Servern verfügbar sind.

1. Load Balancing:  
    Recherchiere, wie man Load Balancing für PostgreSQL einrichten kann.
    Integriere ein Load Balancing-Tool (z.B. PgBouncer oder HAProxy) in deine Docker Compose Datei.
    Teste das Load Balancing, indem du mehrere Anfragen an die Datenbank stellst und überprüfst, wie die Last verteilt wird.

## Sicherheit und Zugriffskontrolle

1. SSL-Verschlüsselung:  
    Lese dich in die SSL-Verschlüsselung für PostgreSQL ein.
    Konfiguriere den PostgreSQL-Container so, dass er SSL-Verbindungen akzeptiert.
    Stelle sicher, dass die Verbindung zwischen PGAdmin und PostgreSQL über SSL erfolgt.

1. Benutzer- und Rechteverwaltung:   
    Erstelle mehrere Benutzer mit unterschiedlichen Rechten in der PostgreSQL-Datenbank.
    Teste die Zugriffskontrolle, indem du prüfst, welche Aktionen die verschiedenen Benutzer durchführen können.

## SSO Anbindung

1.  SingleSignOn (SSO) System auswählen:  
    Recherchiere was ein SSO System ist. 
    Welche SSO Systeme gibt es, vielleicht kennst du schon einige davon.
    Entscheide dich für ein System.

1. Einrichtung des Services:  
    Richte das von dir ausgewähle SSO System in deiner Docker Compose ein.

1. Anbindung an vorhandene Systeme:  
    Deine Docker Compose bietet bereits einige Services an. Recherchiere ob du diese mit SSO betreiben kannst.
    Binde dein SSO System an die Services an die dies unterstützen.