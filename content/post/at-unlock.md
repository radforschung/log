---
title: AT+UNLOCK?
slug: at-unlock
date: 2018-03-19 00:00:00 +0000

---
J, der Hersteller eines unserer Forschungsschlösser, baut nicht nur Fahrradschlösser, sondern hat wohl bereits jahrelange Erfahrung im Bau von Auto-GPS-Trackern.

Glücklicherweise findet man zu diesen Trackern mehr Dokumentation im Internet, als bislang zu *smarten* Fahrradschlössern.

So stellte sich nach Austausch der Chinesischen SIM-Karte durch eine zufällig ausgewählte Prepaidkarte aus der Schublade heraus, dass unser Schloss auch auf SMS reagiert.

Auf `STATUS#` wird mit `Battery:4.08V,NORMAL; GPRS:Link Up GSM Signal Level:Strong; GPS:OFF; LOCK:OFF; BT MAC:██:██:██:██:██:██;` reagiert

`WHERE#` gibt die Position zurück: `Current position! Lat:N48.396019,Lon:E9.990032,Course:232.68,Speed:0.87Km/h,DateTime:2018-03-19 19:49:18`

Es gibt noch weitere Kommandos, die teilweise *"Authentifizierung"* benötigen. Diese passiert aber nur über die Handynummer, die vorher als SOS oder CENTER-Nummer hinterlegt werden muss -- und Nummern hinterlegen klappt ohne weitere Authentifizierung.

Zudem scheint es für die Auto-GPS-Tracker-Versionen auch noch Kommandos zu geben, um den Stromzufuhr der Kraftstoffpumpe zu unterbrechen.

Ein entsperren des Fahrradschlosses hat bis jetzt leider noch nicht funktioniert: `UNLOCK#` gab bislang nur `Error!` zurück.