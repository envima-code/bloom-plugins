---
name: bloom-lca
description: Fragen zu Ökobilanzen, CO2-Fußabdruck oder PCF der eigenen Produkte mit den Bloom-Tools beantworten. Nutzen, wenn jemand nach LCA-Modellen, Emissionen je Lebenszyklusphase, Hotspots oder Vergleichen von Produkten in Bloom fragt.
---

# Bloom LCA

1. Modell finden: `list_models`. Passt der Name nicht eindeutig, die Kandidaten nennen und nachfragen.
2. Aufbau zeigen: `get_model` liefert Phasen, Positionen, Mengen und Datenquellen.
3. Rechnen: `calculate_model`. Für den CO2-Fußabdruck `IPCC 2021`, für alle Wirkungskategorien `EF v3.1`.

Regeln:

- Zahlen nur aus `calculate_model` übernehmen, nie selbst schätzen oder umrechnen.
- Methode, Modellname und Phase immer mit angeben, damit das Ergebnis nachvollziehbar bleibt.
- Die größten Positionen (`topContributors`) als Hotspots nennen.
- Die Tools lesen nur. Wünsche zum Ändern an die Bloom-App verweisen.
