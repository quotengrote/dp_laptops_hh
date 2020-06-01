# Speicherplatz anzeigen
## df
disk free zeigt den freien, also verfügbaren, Speicherplatz auf der Festplatte an.
* Freien Speicherplatz des gesamten Dateisystems anzeigen:

	`df -h`
* Freien Speicherplatz des lokalen Dateisystems anzeigen:

	`df -hl`
## du
disk usage zeigt den belegten, nicht verfügbaren, Speicherplatz auf der Festplatte an.
* Gesamten belegten Speicherplatz des Systems anzeigen:

	`du -sh /`
* Belegten Speicherplatz des Ordners Media anzeigen, ohne *.bmp Dateien zu berücksichtigen:

	`du --exclude="*.bmp*" -sh media/`
* Belegten Speicherplatz des aktuellen Verzeichnisses anzeigen:

	`du -sh ./`
* Sortierung des belegenten Speicherplatz mit maximaler Rekursions-Tiefe von 1:

	`du -h --max-depth 1 ./ | sort -h`

* aus [ThomasKrenn](https://www.thomas-krenn.com/de/wiki/Festplattenbelegung_unter_Linux_in_der_Konsole_mit_df_und_du_anzeigen)
