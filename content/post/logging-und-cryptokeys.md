---
title: Logging und Cryptokeys
date: 2018-04-09 00:00:00 +0000

---
<blockquote class="twitter-tweet"><p lang="de" dir="ltr">*wrrrwrrrwrr-KLACK* und soeben hat sich das zweite Schloss zum ersten mal per BLE öffnen lassen. Der Hersteller hatte einen anderen Key als bislang kommuniziert hinterlegt</p>&mdash; radforschung (@radforschung) <a href="https://twitter.com/radforschung/status/983360948932153344?ref_src=twsrc%5Etfw">April 9, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Nach dem *Chinese New Year*-Urlaub des Herstellers J haben sie uns glücklicherweise mitgeteilt, dass wir doch das blaue Drähtchen am USB-Seriell-Adapter mit Masse verbinden müssen, damit das Schloss auch auf serielle Befehle reagiert.

Freundlicherweise lässt sich nun auch das Logging-Level der Firmware um einiges nach oben drehen -- so zeigt das Log nun auch, was wir per Bluetooth gesendet haben und was es davon wieder entschlüsselt hat. Zusätzlich wurde dann auch recht schnell klar, dass der AES-Key, der in der Dokumentation stand, keinesfalls der war, den das Schloss auch hinterlegt hat - denn beim Start wirft es nun auch den eingestellten Key ins Log. Dieser Key war dann auch im Firmwaredump nochmal klar zu finden.

Das Bluetooth LE-Notification-Problem von V hat leider auch Hersteller J erwischt - auch hier hat das Öffnen des Schlosses mit macOS oder iOS bislang nicht geklappt. So musste auch hier erstmal wieder der Raspberry Pi mit `bluetoothcli` und `gatttool` herhalten.