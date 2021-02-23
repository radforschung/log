---
title: Es öffnet sich!
slug: es-oeffnet-sich
date: 2018-08-26 00:00:00 +0000

---

In den letzten Tagen wurde kräftig an der Entwicklunggeschwindigkeit geschraubt. Wir haben Prototypen zusammengelötet und uns kräftig mit den Innereien des Arduino-Frameworks für den ESP32 beschäftigt.

<blockquote class="twitter-tweet"><p lang="de" dir="ltr">🔑 → Browser → Server → TheThingsNetwork  → LoRa → Schloss öffnet sich \o/ <a href="https://t.co/pHY3IxYQwV">pic.twitter.com/pHY3IxYQwV</a></p>&mdash; radforschung (@radforschung) <a href="https://twitter.com/radforschung/status/1033739633048408064?ref_src=twsrc%5Etfw">August 26, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Das wichtigste Feature - über LoRaWAN das Schloss entsperren - funktioniert nun. Zudem ist eine Prototyp/Debugoberfläche entstanden, die die Daten aus dem TheThingsNetwork verarbeitet und letzte Nachricht, Schlosstatus und Standort anzeigen kann.

Jetzt geht es weiter mit den [nächsten Dingen auf der TODO](../todo/): Anbindung eines GPS-Moduls und eines e-Paper-Displays und weitere Umstellungen auf Interrupts und FreeRTOS-Tasks. Dann klappt es auch mit dem Ziel, den ESP möglichst oft und lange im Low-Power-Modus betreiben zu können.