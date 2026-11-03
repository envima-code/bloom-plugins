---
name: bloom-lca
description: Fragen zu Ökobilanzen, CO2-Fußabdruck oder PCF der eigenen Produkte mit den Bloom-Tools beantworten. Nutzen, wenn jemand nach LCA-Modellen, Emissionen je Lebenszyklusphase, Hotspots, Vergleichen von Produkten, Datenqualität (DQR) oder Berichten (PCF-Bericht, One-Pager, Catena-X, Excel) in Bloom fragt.
---

# Bloom LCA

1. Modell finden: `list_models`. Passt der Name nicht eindeutig, die Kandidaten nennen und nachfragen.
2. Aufbau zeigen: `get_model` liefert Phasen, Positionen, Mengen und Datenquellen.
3. Rechnen: `calculate_model`. Für den CO2-Fußabdruck `IPCC 2021`, für alle Wirkungskategorien `EF v3.1`.
4. Datenqualität: `get_data_quality`, mit `standard` = `pefcr`, `iso14067` oder `catenax`, ohne Angabe alle drei.
   Eine kleinere Note ist besser, 5 ist die schlechteste (nicht bewertete Daten zählen als 5).
5. Bericht: `export_report` mit `format` (`pcf-docx`, `pcf-onepager`, `pef-onepager`, `pcf-catena-x`, `xlsx`,
   `csv`). Welche Formate passen, steht in `get_data_quality` unter `supportedFormats`. Den Download-Link und seine
   Ablaufzeit nennen, er gilt 15 Minuten.

Regeln:

- Zahlen nur aus `calculate_model` übernehmen, nie selbst schätzen oder umrechnen.
- Methode, Modellname und Phase immer mit angeben, damit das Ergebnis nachvollziehbar bleibt.
- Die größten Positionen (`topContributors`) als Hotspots nennen.
- Datenqualität und Berichte kommen aus der letzten gespeicherten Berechnung. Meldet ein Tool, dass sie fehlt, bitten,
  das Modell in Bloom zu berechnen und zu speichern.
- Die Tools ändern keine Modelle. Wünsche zum Ändern an die Bloom-App verweisen.
