---
title: Bikesharing, selbstgemacht
date: 2018-04-25

---

Als wir die Fahrradschlösser-Samples bestellt hatten, wollten wir uns eigentlich nur die Sicherheit der Schlösser, der Apps und der Kommunikation zwischen diesen ansehen.

Nun stand aber im [Verschwörhaus](https://verschwoerhaus.de) schon seit längerer Zeit ein Lastenfahrrad mit Elektroantrieb rum. Dieses -- und das Problem, dass in Ulm bislang kein Bikesharing-Anbieter der *"4ten Generation"* (möglichst Stationslos, Anmeldung und Entleihe per App, 24/7 verfügbar) existiert -- brachte uns auf die Idee, mal zu erforschen, wie Bikesharing 2018 eigentlich aussehen müsste.

Ulm als Experimentierstandort ist dabei (für uns) interessant:

* Es gibt bislang einen Fahrradverleih für Gruppen, der eine Buchung vorab benötigt und nur innerhalb der Öffnungszeiten der Touristeninformation funktioniert.
* Einzelne Fahrradhändler bieten einen ähnlichen Service an, der aber auch an deren Öffnungszeiten gebunden ist.
* Die Universität Ulm liegt auf dem Eselsberg (wie der Name schon sagt: auf einem Berg!) - das hat bislang kommerzielle Anbieter davon abgehalten, ihre Systeme auszurollen, da der Transport von der Stadtmitte wieder auf den Berg wohl nicht rentabel ist.
* Die Innenstadt ist recht ebenerdig, außenrum wird es hügeliger. Ein Elektroantrieb wären also hilfreich.
* car2go hat 2014 Ulm verlassen. Damit existieren zwar mit einem lokalen Anbieter und Flinkster weiterhin Car-Sharing-Systeme, diese sind jedoch beide Stationsbasiert.
* Es gibt Einkaufsmöglichkeiten in der Innenstadt und einen Ikea sowie weitere Baumärkte und Einzelhändler in der Weststadt, die gut per (Lasten-)Fahrrad erreichbar wären.
* Ein bestehendes IoT-Netzwerk mittels [TheThingsNetwork/LoRaWAN](https://lora.ulm-digital.com) mit guter Abdeckung ist offen und kostenfrei verfügbar.

Wir haben nun also Schlosshardware und eine Stadt, die durchaus ein flexibles und modernes Bikesharingsystem vertragen könnte.

Wie würden wir aber nun an so eines kommen? Für kommerzielle Anbieter aus Deutschland wie DB Connect (*Call a bike*) und Nextbike ist Ulm aufgrund der Hügel wohl eher uninteressant, für die Anbieter aus Asien wie obike, ofo, mobike usw. ist Ulm von der Einwohnerzahl wohl auch noch zu klein.

Eine aus unserer Sicht gute Lösung müsste also folgende Punkte erfüllen:

* möglichst Stationslos
* per App entleihbar
* 24/7 verfügbar (ja, auch nachts)
* Pedelecs als Fahrräder
* im besten Falle auch Lastenfahrräder, Fahrradanhänger, Transportmöglichkeiten etc.
* Open Source ([*public money, public code!*](https://publiccode.eu/de/), auch weil wir Verbesserungen selbst beitragen wollen)
* genug Fahrräder in der Stadt
* von anderen Städten wiederverwendbar (je mehr Bikesharing überall, desto besser)
* möglichst wenig Kosten für den Betrieb (keine M2M-SIM-Karten mit monatlichen Gebühren)

Passenden Open-Source-Lösungen, um so etwas selbst zu bauen, haben wir bislang leider keine gefunden. Es gibt durchaus Lösungen, die teilweise auch App-basierend wären - dann jedoch auf einfache Zahlenschlösser zurückgreifen. Oder Lösungen, die dann wieder auf die Öffnungszeiten von kleinen Läden zurückgreifen und mündlich rotierende Code-Wort-Listen abgleichen.

Auch interessierte Verschwörhausmitbewohner\*innen und -besuchende sehen durchaus einen Bedarf für ein modernes, offenes Bikesharingsystem.

**Also bauen wir es wohl selbst**.

Wir sind mit dieser Idee (und der Schlosshardware) zum [*Digital Mobility Hack*](https://vm.baden-wuerttemberg.de/de/verkehrspolitik/zukunftskonzepte/digitale-mobilitaet/digital-mobility-hack-bw/) des Verkehrsministeriums Baden-Württemberg gefahren. An einem Wochenende haben wir die Öffnung per Bluetooth in eine Android-App verpflanzt, einen groben Prototypen zur Fahrrad- und Schlossverwaltung in django begonnen und versucht einen ESP32 mit LoRaWAN mit dem Schloss zu verbinden.

{{< tweet 989149856685068292 >}}

Unsere Abschlusspräsentation dazu, die hoffentlich das Thema kurz vermittelt, sah dann so aus:

{{< speakerdeck 8d3f451f651f4d61b2ad74d5385df195 >}}

Glücklicherweise hat das Konzept die dort anwesende Jury überzeugt - und wir erhalten das [*Mobilitätsstipendium BW*](https://vm.baden-wuerttemberg.de/de/verkehrspolitik/zukunftskonzepte/digitale-mobilitaet/mobilitaetsstipendium-bw/), was uns ermöglicht, noch tiefer in die *radforschung* einzusteigen.

{{< tweet 987787804561346560 >}}
