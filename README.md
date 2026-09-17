# Bloom für Claude und ChatGPT

Verbindet [Bloom](https://envima.de), das LCA-Werkzeug der envima GbR, mit Claude und ChatGPT. Danach lassen sich im
Chat die eigenen Ökobilanz-Modelle auflisten, ansehen und mit Bloom berechnen.

> **Vorschau.** Die Verbindung zeigt auf das Staging-System von Bloom (`service.envima.de/bloom-staging`), nicht auf die Produktion.

## Was die Verbindung kann

| Werkzeug | Zweck |
|---|---|
| `list_models` | eigene LCA-Modelle auflisten |
| `get_model` | Phasen, Positionen, Mengen und Datenquellen eines Modells |
| `calculate_model` | CO2-Fußabdruck bzw. Wirkungskategorien je Phase, mit den größten Positionen |

Die Werkzeuge lesen nur. Die Zahlen rechnet Bloom, nicht das Sprachmodell.

## Sicherheit

- Anmeldung mit dem eigenen Bloom-Konto auf der Bloom-Seite. Das Passwort sieht weder Claude noch ChatGPT.
- Jede Person sieht nur ihre eigenen Modelle.
- Ein Passwortwechsel in Bloom beendet die Verbindung.

## Installieren

**Claude** (bezahlter Plan): Anpassen → Plugins → Persönliche Plugins → **+** → Marktplatz hinzufügen → aus Repository,
`envima-code/bloom-plugins` eintragen, dann das Plugin **bloom** installieren und mit dem Bloom-Konto anmelden.

**ChatGPT Desktop** (bezahlter Plan): Plugins → **Add** → Add plugin marketplace, Quelle `envima-code/bloom-plugins`,
Git ref `master`, dann **Bloom** installieren und anmelden.

**Claude Code:**

```
/plugin marketplace add envima-code/bloom-plugins
/plugin install bloom@envima
```

## Beispiele

- „Welche LCA-Modelle habe ich in Bloom?“
- „Berechne den CO2-Fußabdruck von Fitness Tracker (Demo) je Lebenszyklusphase.“
- „Welche Positionen verursachen die meisten Emissionen?“

## Aufbau

| Datei | Für |
|---|---|
| `.claude-plugin/marketplace.json`, `plugins/bloom/.claude-plugin/plugin.json`, `plugins/bloom/.mcp.json` | Claude |
| `.agents/plugins/marketplace.json`, `plugins/bloom/plugin.json`, `plugins/bloom/mcp.json` | ChatGPT |
| `plugins/bloom/skills/bloom-lca/SKILL.md` | Hinweise für beide, wie die Werkzeuge zu nutzen sind |
