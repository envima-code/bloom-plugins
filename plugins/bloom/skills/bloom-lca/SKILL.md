---
name: bloom-lca
description: Fragen zu Ökobilanzen, CO2-Fußabdruck oder PCF der eigenen Produkte mit den bloom-Tools beantworten. Nutzen, wenn jemand nach LCA-Modellen, Emissionen je Lebenszyklusphase, Hotspots, Vergleichen von Produkten oder Berichten (PCF, One-Pager) in bloom fragt.
---

# bloom LCA

1. Modell finden: `list_models`. Passt der Name nicht eindeutig, die Kandidaten nennen und nachfragen.
2. Aufbau zeigen: `get_model` liefert Phasen, Positionen, Mengen und Datenquellen.
3. Rechnen: `calculate_model`. Für den CO2-Fußabdruck `IPCC 2021`, für alle Wirkungskategorien `EF v3.1`.
4. Berichte und Datenqualität: `get_data_quality` und `export_report` nutzen das in bloom gespeicherte Ergebnis.
   Fehlt es, ist es veraltet oder passt die Methode nicht (z. B. braucht der PEF-One-Pager EF 3.1), zuerst den
   Nutzer fragen, ob neu gerechnet und gespeichert werden soll, und erst nach dem Ja `calculate_and_save_model`
   aufrufen. Ohne Methode wählt bloom die passende.

Regeln:

- Zahlen nur aus `calculate_model` übernehmen, nie selbst schätzen oder umrechnen.
- Methode, Modellname und Phase immer mit angeben, damit das Ergebnis nachvollziehbar bleibt.
- Die größten Positionen (`topContributors`) als Hotspots nennen.
- `calculate_and_save_model` ersetzt das bisher gespeicherte Ergebnis: nie ohne Rückfrage aufrufen. Lehnt bloom die
  Methode ab, die Begründung nennen (z. B. Zielrahmen in bloom wechseln), nicht mit einer anderen Methode raten.
- Die Modelle selbst ändern die Tools nicht. Wünsche zum Ändern an die bloom-App verweisen.
