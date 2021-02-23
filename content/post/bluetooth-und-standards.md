---
title: Bluetooth und Standards
date: 2018-04-09 00:00:00 +0000

---
Bei dem Schloss von V war durch die Dokumentation recht schnell klar, wie wir über Bluetooth es zum Öffnen bringen.

Erste Versuche mit [WebBluetooth](https://developers.google.com/web/updates/2015/07/interact-with-ble-devices-on-the-web) waren aber leider nicht erfolgreich - so bekamen wir beim Versuch Notifications für eine Characteristic zu erhalten nur `DOMException: GATT Error: Not supported.` zurück.

Nach Debugging mit dem *Bluetooth Explorer* aus den *XCode Hardware IO Tools* stellt sich heraus: der Hersteller hat Bluetooth LE nicht richtig implementiert. So fehlt der [*Client Characteristic Configuration descriptor*](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.descriptor.gatt.client_characteristic_configuration.xml), der es überhaupt erst ermöglicht, sich auf Characteristic Notifications zu subscriben.

Unter Android scheint das kein Problem zu sein, da dort die mitgelieferte Service-App auch wunderbar ohne funktioniert -- WebBluetooth in Chrome und Experimente mit [noble für node.js](https://github.com/noble/noble) unter macOS scheitern aber daran.

<blockquote class="twitter-tweet"><p lang="de" dir="ltr">Ey, Schlosshersteller. BLE anzubieten, bedeutet auch, die _ganze_ BLE-Spezifikation zu implementieren. Nicht einfach Dinge weglassen und hoffen, dass es unter Android schon tut und woanders naja</p>&mdash; radforschung (@radforschung) <a href="https://twitter.com/radforschung/status/981607541879820289?ref_src=twsrc%5Etfw">April 4, 2018</a></blockquote>

Android bietet mit dem [*Bluetooth HCI Snoop Log*](https://stackoverflow.com/questions/23877761/sniffing-logging-your-own-android-bluetooth-traffic) (aktivierbar in den Entwickleroptionen) auch noch eine komfortable Möglichkeit zu sehen, was da eigentlich so über die Luft zum und vom Schloss kommuniziert wird. Dieses Snoop Log und [frida](https://www.frida.re), einem Toolkit, um u.a. Funktionsaufrufe in bereits laufenden Apps (ohne den Sourcecode zu kennen) zu tracen, waren nun sehr hilfreich. So konnten wir die Kommandos in der Dokumentation mit denen, die die Service-App so verschickte und das Schloss öffneten, vergleichen.

Zu einem geöffneten Schloss haben uns dann die Experimente mit blueZ auf einem Raspberry Pi[^1] gebracht: mit einer Mischung aus `bluetoothctl`, um Notifications zu abonnieren, und `gatttool`, um auf eine Characteristic zu schreiben, hat sich das Schloss zum ersten Mal ohne die Service-App geöffnet.

<blockquote class="twitter-tweet"><p lang="de" dir="ltr">Montag morgen, kurz nach 2 Uhr früh. Das erste Schloss hat sich nun endlich dazu überreden lassen, per Bluetooth aufzusperren 🔓🎉</p>&mdash; radforschung (@radforschung) <a href="https://twitter.com/radforschung/status/983139822721171457?ref_src=twsrc%5Etfw">April 9, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

[^1]: dazu extra blueZ selbst kompiliert, um auszuschließen, dass die veraltete Version aus den Raspbian-Paketquellen irgendwelche Notification-Bugs mitbringt