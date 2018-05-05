---
title: Logging und Cryptokeys
date: 2018-04-09

---

{{< tweet 983360948932153344 >}}

Nach dem *Chinese New Year*-Urlaub des Herstellers J haben sie uns glücklicherweise mitgeteilt, dass wir doch das blaue Drähtchen am USB-Seriell-Adapter mit Masse verbinden müssen, damit das Schloss auch auf serielle Befehle reagiert.

Freundlicherweise lässt sich nun auch das Logging-Level der Firmware um einiges nach oben drehen -- so zeigt das Log nun auch, was wir per Bluetooth gesendet haben und was es davon wieder entschlüsselt hat. Zusätzlich wurde dann auch recht schnell klar, dass der AES-Key, der in der Dokumentation stand, keinesfalls der war, den das Schloss auch hinterlegt hat - denn beim Start wirft es nun auch den eingestellten Key ins Log. Dieser Key war dann auch im Firmwaredump nochmal klar zu finden.

Das Bluetooth LE-Notification-Problem von V hat leider auch Hersteller J erwischt - auch hier hat das Öffnen des Schlosses mit macOS oder iOS bislang nicht geklappt. So musste auch hier erstmal wieder der Raspberry Pi mit `bluetoothcli` und `gatttool` herhalten.