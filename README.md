# formverliebt · Öffentliche Plugin-Updates

Hier werden ausschließlich fertige Installationspakete, Versionshinweise und das tokenfreie Update-Manifest veröffentlicht. Die Entwicklung und deren Historie werden separat geführt. Die ZIPs sind öffentlich herunterladbar; sie enthalten keine Kunden-Datenbanken oder Zugangsdaten.

## Aktuelle Beta

- **Kundenwebsites:** [formverliebt Agent 3.0.3-beta.1](https://github.com/looneymp3/formverliebt-updates/releases/download/v3.0.3-beta.1/formverliebt-3.0.3-beta.1.zip)
- **Zentrale:** [Agency Manager 1.0.3-beta.1](https://github.com/looneymp3/formverliebt-updates/releases/download/v3.0.3-beta.1/formverliebt-manager-1.0.3-beta.1.zip)

WordPress → Plugins → Installieren → Plugin hochladen. Bei bestehender Installation die vorhandene Version **direkt ersetzen**, nicht zuvor deinstallieren. Die Ersetzung von 2.6.5 durch den Agent3 wurde einschließlich AI-Kennzeichnungs-Einstellungen, Bild-Metadaten und bestehender Verbindung lokal geprüft.

Der Manager läuft auf einer separaten WordPress-Instanz im Vollbild; „Zurück zu WP“ öffnet die normale Administration. Im Manager Verbindungscode erstellen und auf der Kundenwebsite unter „Mit Netzwerk verbinden“ eintragen. Aufträge kontaktieren die Kundenwebsite sofort und übertragen das Inventar danach neu. Der regelmäßige Hintergrundabgleich bleibt als Rückfallweg erhalten. Ändernde Fernfunktionen werden pro Kundenwebsite einmal freigegeben.

Weitere Plugin-Updates erscheinen regulär in WordPress. Ein GitHub-Token ist nicht erforderlich. Beta-Installationen nutzen standardmäßig den Beta-Kanal. Der Updater kontrolliert Produkt-/Versionszuordnung und SHA-256 vor Installation.

## Beta-Grenzen

Enthalten sind Organisation/Kategorien/Wartung/Priorität, Fernaufträge, zentrale Updates, verschlüsselte lokale Backups mit Zeitplänen, Konfigurations-/Core-Prüfungen, HTTP-Monitoring, Plugin-Steuerung und Benutzeraktionen.

Es handelt sich um eine begrenzte Beta, keinen vollständigen ManageWP/MainWP-Ersatz:

- Backups: Einzelinstallationen, maximal 64MiB pro Datei/4MiB pro DB-Zeile; keine transaktionale DB-Aufnahme. Große Archive können Hosting-Limits erreichen. Wiederherstellung derzeit manuell; SQL-Chunks in Nummernfolge importieren. Verschlüsselungsschlüssel separat aufbewahren.
- Lokaler Backup-Speicher außerhalb des Webverzeichnisses; temporärer Hosting-Speicher kann bereinigt werden. Kein vorkonfigurierter externer S3-Speicher oder automatischer Restore.
- Kein externer Malware-/Vulnerability-Datenbankabgleich. Ein unauffälliger Konfigurationscheck garantiert keine sichere Website.
- HTTP-Monitoring mit TLS-Verifikation, ohne Zertifikatsablaufprüfung. Fünf Websites pro Fünfminuten-Durchlauf. Automatik benötigt WordPress-Cron/Server-Cron.
- Verändernde Multisite-Aktionen sind deaktiviert. Benutzeraktionen übertragen keine Passwörter.

Vor Einsatz auf wichtigen Websites zuerst in einer separaten Testinstallation prüfen und ein unabhängiges Backup vorhalten.

Neu: Jede Website hat eigene Tabs für Plugins/Updates, Backups, Sicherheit, Fernsteuerung, Benutzer, Kundendaten und Aufträge. Globale Modul-Seiten dienen Sammelaktionen für bis zu zehn Websites. Echte lokale HTTP-Proben bestätigten Aktivierung/Deaktivierung samt neuem Inventar in unter zwei Sekunden ohne manuelles Synchronisieren oder Cron-Aufruf; eine Laufzeitgarantie für fremde Hosts ist dies nicht.
