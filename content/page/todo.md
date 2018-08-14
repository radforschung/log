---
title: "TODO"
slug: todo
date: 2018-07-28 00:00:00 +0000

---


### Schlosshardware & Firmware:

- [x] Schlosshardware aus China, Motor aus China, Akku aus China, Platine ist raus
- [x] Schlossmotor ansteuern
- [x] feststellen ob Schloss offen / geschlossen
- [x] passende Motorumdrehungen auslösen, bis Schloss offen
- [ ] Ladeschaltung für bestehenden Akku

#### lora
- [x] erste lorawan-anbindung für ping
- [x] lorawan um schlossstatus zu übertragen
- [ ] lorawan um schloss zu öffnen
- [ ] lorawan um bestätigung, wenn geöffnet versenden
- [ ] lorawan um device neu zu starten
- [ ] lorawan um schloss in den wartungsmodus (nicht ausleihbar) zu versetzen
- [ ] e2e crypto über lorawan drüberlegen

#### ladeschaltung
- [ ] ladeschaltung mit akkustandserfassung finden
- [ ] ladestatus des akkus erfassen
- [ ] ladestatus per lorawan versenden
- [ ] kritische ladelevel definieren

#### ortung
- [ ] gps-modul anbinden
- [ ] lorawan um aktuelle gps position zu übertragen
- [ ] wifi-ortung
- [ ] kompression für wifi-ortung suchen
- [ ] lorawan um wifi-ortungsdaten zu übertragen
- [ ] gsm-modul für basisstationsortung
- [ ] nochmal nach preisgünstigem lte-modul suchen
- [ ] lorawan um gsm/lte-basisstationsids zu übertragen

#### bewegung
- [ ] gyroskop verbauen
- [ ] bewegung, wenn verschlossen mitbekommen
- [ ] bewegungsalarm per lorawan versenden

#### nfc-unlock
- [ ] nfc-reader verbauen
- [ ] nfc-uid lesen
- [ ] nfc-uid per lorawan versenden

#### e-paper
- [ ] e-paper-display ansteuern
- [ ] qr-code auf e-paper-display anzeigen
- [ ] öffnungsstatus anzeigen
- [ ] nicht ausleihbar anzeigen
- [ ] nfc-bitte-warten anzeigen
- [ ] nfc-nicht-erkannt anzeigen
- [ ] nfc-nicht-akzeptiert anzeigen
- [ ] akku leer anzeigen
- [ ] fehlercode anzeigen

#### lautsprecher
- [ ] lautsprecher ansteuern
- [ ] lorawan um lautsprecher klingeln zu lassen
- [ ] happy song nach entsprerren
- [ ] happy song nach zuschließen

#### led
- [ ] rgb-led verbauen
- [ ] rgb-led ansteuern

#### low-power
- [ ] deep-sleep ermöglichen
- [ ] low-power-optimierungen
- [ ] periodisch aufwecken, standort und akkustand senden
- [ ] bei bewegung aufwecken
- [ ] bei nfc aufwecken
- [ ] bei bluetooth le aufwecken?
- [ ] aufwecke-schalter/touchscreen?

#### ladeinfrastruktur
- [ ] gedanken über lademöglichkeit machen
- [ ] solarzelle anbinden

#### update
- [ ] firmwareupdatemodus
- [ ] firmware via wifi downloaden
- [ ] firmware uploaden können

#### platine
- [ ] stecker/buchsen für motor, schalter herausfinden
- [ ] eigene platine layouten
- [ ] erste eigene platinen bestellen, ausprobieren
- [ ] wie bekommen wir das gehäuse wasserdicht?

### Schlossendpoint:

- [ ] schlösser registrieren
- [ ] logging von allen nachrichten

#### status
- [ ] eingehenden schlossstatus annehmen
- [ ] schlosstatus speichern

#### öffnen
- [ ] schlossöffnung per lora versenden
- [ ] eingehende bestätigung annehmen

#### alarm
- [ ] eingehenden schlossalarm annehmen
- [ ] schlossalarm per http weitergeben

#### location
- [ ] eingehende gps-koordinaten annehmen
- [ ] schlossposition speichern
- [ ] eingehende wifi-macadressen annehmen
- [ ] eingehende gsm/lte-basisstationsids annehmen
- [ ] mozilla location services anfragen

#### nfc-unlock
- [ ] eingehende nfc-uid annehmen
- [ ] nfc-uid weitergeben (check nicht auf diesem endpoint)
- [ ] schlossöffnung versenden
- [ ] fehlercode versenden

###  Orga:

- [ ] Mehr Schlösser bestellen bzw. verhandeln, um nur Schlossrohling zu bekommen
- [ ] Schloss an Testfahrrad befestigen können
- [ ] Platz für Solarzelle finden
- [ ] Verkabelung am Fahrrad klären
