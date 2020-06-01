# Laptops HH für Ausbildung

## Austattung
- 1x USB-Stick "c't Notfall Windows"
- 1x externe USB-Festplatte mit/für das Image

## Installation
- Nutzer: "user01"
- Passwort: "hallowelt"
- Hostname: "Laptop001Linux/Laptop001Windows"

### Vor Installation
- WLAN-Schalter auf: "ON"
- BIOS Passwort wenn vorhanden abschalten
- Bootreihenfolge anpassen falls notwendig

### Windows installieren
- Cave: Erst Windows, dann Linux, sonst überschreibt Windows den Bootloader
- Keine Aktivierung vornehmen, diese erfolgt nach dem Imagen
  - Version muss zum Lizenzaufkleber unter dem Laptop passen
- Hostname wird auch nach dem Imagen angepasst
- Standardinstallation
  - Platz für zweite bzw. die Linux Partition lassen
- Cave: Offline-Konto anlegen!
- Benötigte Progamme installieren:
  - Lego Mindstorms EV3
  - Arduino IDE
  - Android Studio
  - Virtual Box
  - Libre Office
- Windows Tools entfernen/deaktivieren
  - Cortana
  - Fragen bei Setup mit "nein" beantworten
  - Fujitsu Tools im Autostart deaktivieren


### Installieren Linux
Cave: Teile der Rechner starten nicht vom linken USB-Port, falls USB überhaupt nicht geht, Installation per CD.
- Standardinstallation in freien Speicherplatz "neben" Windows.
- Benötigte Progamme installieren:
  - htop
  - mc
- sudo apt update && sudo apt upgrade

## Imagen
### Sichern/Imagen des Musterlaptops
Bootauswahl ist mit F12 zu erreichen.
1. Start Windows-Notfall-Stick
2. Start Macrium Reflect
3. Datensicherung
4. "Abbild von ausgewählten Datenträger..."
5. lokale Festplatte auswählen(mit allen Partitionen)
6. Zielordner auf externe Festplatte auswählen
7. starten
8. Fertig...

### Rückspielen/Imagen der Musterlaptops
Bootauswahl ist mit F12 zu erreichen.
1. Start Windows-Notfall-Stick (zum starten von Notfallstick nur stick anschließen)
2. Sobald Notfall-Windows hochgefahren: festplatte mit .mrimg anschließen (am besten am USB 3.0 Port links am Laptop)
2. Start Macrium Reflect (Pfad: Start>Alle Programme>Utilities>Macrium Reflect)
3. Sprache auswählen (eingabe bestätigen)
4. Reiter "Wiederherstellen" auswählen
4. Auf "Abbild- oder Sicherungsdatei zur Wiederherstellung suchen" klicken
4. .mrimg auf festplatte suchen und auswählen, mit "OK" bestätigen
5. Auf "Wiederherstellung" klicken
6. Auf "Select a disk to restore to..." klicken
7. Rechner interne Festplatte auswählen (Bsp: TOSHIBA MK5061...)
8. Alle Partitionen zum überschreiben auswählen
9. Quelle: externer USB-Festplatten Pfad mit .mrimg-Datei
10. Ziel: interne Festplatte
10. Auf "Weiter" klicken
10. Auf "Fertigstellen" klicken
11. Fenster "Überschreibungvorgang bestätigen" Hacken setzen und auf "Weiter..." klicken
11. Warten (sobald sich Windows Explorer öffnet einfach schließen oder ignorieren)
12. wenn gefragt wird ob Datenträger formatiert werden soll "Abbrechen" klicken
13. Sobald Imagen fertig ist alle Fenster schließen und Rechner herunterfahren

### nach dem Imagen
* Hostnamen in Linux und Windows anpassen
1. Zuerst ins Windows Booten und Hostname unter Einstellungen>System>Info>Diesen PC umbenennen
2. PC neustarten und ins Linux booten
3. Hostname mit `sudo nano /etc/hostname` ändern und herunterfahren
  * Muster: laptop<laufende_nummer>linux / laptop<laufende_nummer>windows
  * Beispiel: `laptop004linux`
