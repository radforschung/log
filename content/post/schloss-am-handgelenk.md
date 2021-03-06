---
title: Schloss am Handgelenk
slug: schloss-am-handgelenk
date: 2018-04-02 00:00:00 +0000

---
Im Schloss von J ist ein *Mediatek MT2503AV* verbaut. Dieser Chip wird normalerweise in - wer hätte das gedacht - Smartwatches eingesetzt. Er basiert auf der ARMv7-Architektur, bringt GPS, Bluetooth 3.0, ein GPRS Modem und u.a. Support für ein Gyroskop mit.

Zusätzlich würden sich an diesen Chipsatz ein LCD, eine Kamera, ein Audiointerface etc. anschließen lassen. Damit eignet er sich bereits wunderbar für Featurephones - und so findet man bei Aliexpress und in anderen Shops auch durchaus Telefone und Smartwatches, die genau auf diesem Chipsatz basieren.

Mittels dem beiliegendem USB-Seriell-Kabel lässt sich auch etwas Logging ansehen (115200, 8N1):

```
OS■■■■■APP■■■■■■■:342, ■■■■■■■■■■:342

power on
project:GB110

tick:118, count:1
SIM OK

+EBTPRFAC:1

AT+CMGL=0

OK
```

Durch die Verbreitung in Smartwatches hat sich glücklicherweise bereits eine Community zum Firmware-Modding etabliert. So gibt es bei xda-developers einen [Thread zum Auslesen der Firmware](https://forum.xda-developers.com/smartwatch/other-smartwatches/readback-extractor-mtk6260-firmware-t3289272) von kompatiblen Mediatek-Chips.

Dazu wird das Mediatek FlashTool in einer passenden Version, ein Scatterfile (das beschreibt, wie der verbaute Flash aufgeteilt ist) und USB/Seriell-Zugang zum UART des Chips benötigt. Da das benötigte Scatterfile normalerweise mit der Firmware der Smartwatch zum Download angeboten wird, waren wir erstmal auf der Suche nach einem passenden Scatterfile. Glücklicherweise lässt sich das `scatter_for_backup&format_created_by_dfgigger.cfg` aus einem russischem Forenthread über Smartwatch-Modifikationen bei fast allen Chipsätzen verwenden.

<blockquote class="twitter-tweet"><p lang="de" dir="ltr">Oh. Der verbaute SoC wird normalerweise in billigen Smartwatches eingesetzt. Dementsprechend gibt es da schon Tooling - und nun haben wir einen Firmwaredump \o/ <a href="https://t.co/pbmJOML4C1">pic.twitter.com/pbmJOML4C1</a></p>&mdash; radforschung (@radforschung) <a href="https://twitter.com/radforschung/status/975495046953951234?ref_src=twsrc%5Etfw">March 18, 2018</a></blockquote>

Nach einem Neustart des Schlosses durch Abziehen des Akku-Steckers und dem *Read Back* mit dem FlashTool liegt dann eine `ROM_0`-Datei herum. Diese lässt sich mit dem *ReadBack Extractor* aus oben verlinktem xda-developers-Thread in einzelne Dateien aufsplitten, die auch wieder auf das Schloss geflasht werden könnten.

Durch das *Maui META*-Tool, das normalerweise wohl im Werk für die Kalibration von GSM, GPS und co verwendet wird, lässt sich auch auf den FAT-Speicher des Chips zugreifen.

<blockquote class="twitter-tweet"><p lang="de" dir="ltr">Heute gelernt: Eines der Schlösser bietet über ein interessantes Tool auch Zugriff auf den internen FAT-Speicher an. Dort zu finden: Config, Logs und Zertifikate <a href="https://t.co/6lf0tXlZjR">pic.twitter.com/6lf0tXlZjR</a></p>&mdash; radforschung (@radforschung) <a href="https://twitter.com/radforschung/status/980904898631032832?ref_src=twsrc%5Etfw">April 2, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Dort legt die Firmware, die auf einer Mediatek IoT-Plattform basieren zu scheint, Konfiguration, aber vorallem Logs vom GPS ab.
