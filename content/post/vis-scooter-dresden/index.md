---
title: 'Visualisierung: E-Scooter-Fahrten in Dresden'
slug: vis-scooter-dresden
date: 2019-07-26 00:00:00 +0000

---

<video controls autoplay poster="poster.jpg" width="100%">
  <source src="https://radforschung.org/log-content/2019/07/radfoschung_lime_dresden_720.mp4" type="video/mp4" media="all and (max-width: 480px)">
  <source src="https://radforschung.org/log-content/2019/07/radfoschung_lime_dresden_720.webmhd.webm" type="video/webm" media="all and (max-width: 480px)">
  <source src="https://radforschung.org/log-content/2019/07/radfoschung_lime_dresden.mp4" type="video/mp4">
</video>

Der E-Scooter-Anbieter Lime ist gestern, am 25. Juli 2019, in Dresden gestartet.
Wir haben den kompletten ersten Tag die Standorte der Roller mittels der [App-Schnittstelle](https://github.com/ubahnverleih/WoBike/blob/master/Lime.md) gesammelt. Anhand dieser Daten lassen sich Ausleih- und Abgabeort eines Rollers errechnen. Zwischen diesen beiden Punkten haben wir mit Hilfe von OpenStreetMap-Daten jeweils die kürzeste Fahrradroute berechnet - das heißt zwar nicht, dass die Roller wirklich dort entlang gefahren sind, gibt aber eine Vorstellung der ungefähr gefahrenen Strecke. 

Legt man alle Fahrten übereinander erhält man eine Heatmap, an welchen Orten besonders häufig mit den Scootern gefahren wird.
Auf diese Karte haben wir nun noch zeitabhängig die berechnete Fahrt animiert.

Bei Interesse an Rohdaten, Auswertungen oder Visualisierungen für andere Städte [meldet euch gern bei uns](/log/about/).