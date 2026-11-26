---
name: bloom-lca
description: Fragen zu Ökobilanzen, CO2-Fußabdruck oder PCF der eigenen Produkte mit den bloom-Tools beantworten. Nutzen, wenn jemand nach LCA-Modellen, Emissionen je Lebenszyklusphase, Hotspots oder Vergleichen von Produkten in bloom fragt.
---

# bloom LCA

1. Modell finden: `list_models`. Passt der Name nicht eindeutig, die Kandidaten nennen und nachfragen.
2. Aufbau zeigen: `get_model` liefert Phasen, Positionen, Mengen und Datenquellen.
3. Rechnen: `calculate_model`. Für den CO2-Fußabdruck `IPCC 2021`, für alle Wirkungskategorien `EF v3.1`.
4. Bei Bedarf: `get_hotspots` (größte Treiber), `get_data_quality` (Datenqualität, Normerfüllung),
   `list_scenarios` und `compare_scenario` (Was-wäre-wenn), `search_datasets` und `list_saved_matches`
   (passende Datensätze).

Regeln:

- Zahlen nur aus den bloom-Tools übernehmen, nie selbst schätzen oder umrechnen.
- Methode, Modellname und Phase immer mit angeben, damit das Ergebnis nachvollziehbar bleibt.
- Die größten Positionen (`topContributors` bzw. `get_hotspots`) als Hotspots nennen.
- Zwei Tools ändern etwas in bloom, nur nach ausdrücklicher Zustimmung aufrufen:
  `calculate_and_save_model` ersetzt das gespeicherte Ergebnis des Modells, `export_report` legt einen Bericht
  an (der erste Catena-X-Export legt die Firmenangaben für das Modell fest).
- Alles andere lesen die Tools nur. Wünsche, ein Modell zu bearbeiten, an die bloom-App verweisen.
