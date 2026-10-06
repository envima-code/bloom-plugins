# Bloom für Claude und ChatGPT

Verbindet [Bloom](https://envima.de), das LCA-Werkzeug der envima GbR, mit Claude und ChatGPT. LCA steht für
Life Cycle Assessment, auf Deutsch Ökobilanz: die Rechnung, wie viel ein Produkt über sein Leben hinweg an
Umwelt kostet, zum Beispiel wie viel CO2 es verursacht.

Wenn die Verbindung einmal steht, kann man im Chat ganz normal fragen, zum Beispiel "Welche Ökobilanzen habe
ich in Bloom?" oder "Berechne den CO2-Fußabdruck von meinem Produkt", und die KI holt die Antwort direkt aus
Bloom.

Diese Seite erklärt Schritt für Schritt, wie man die Verbindung einrichtet. Kein Vorwissen nötig.

## Was man vorher braucht

1. Ein Bloom-Konto, das das LCA-Modul freigeschaltet hat. Ohne dieses Modul meldet die Verbindung später einen
   Fehler. Im Zweifel bei envima nachfragen.
2. Einen bezahlten Plan bei Claude oder ChatGPT. In den kostenlosen Gratis-Versionen funktioniert die Verbindung
   nicht zuverlässig (bei ChatGPT gar nicht, bei Claude nur stark eingeschränkt).

## Die eine Adresse, die man braucht

Überall, wo unten nach einer Adresse (URL) gefragt wird, gehört genau diese hinein:

```
https://service.envima.de/bloom/mcp
```

Am besten jetzt markieren und kopieren. Wichtig: die Adresse endet auf `/mcp`, und es heißt `/bloom/`, nicht
`/bloom-staging/`. Ein Tippfehler ist der häufigste Grund, warum die Verbindung nicht klappt.

## Einrichten in Claude Desktop

Claude Desktop ist das Claude-Programm für Windows und Mac. Es geht genauso in Claude im Browser.

1. Claude öffnen.
2. Unten links auf den eigenen Namen klicken, dann auf **Einstellungen** (englisch: Settings).
3. Links im Menü auf **Connectors** (teils übersetzt als "Konnektoren") klicken.
4. Auf den Knopf **Benutzerdefinierten Connector hinzufügen** klicken (englisch: Add custom connector). Er steht
   meist ganz unten in der Liste.
5. Es öffnet sich ein kleines Fenster mit zwei Feldern:
   - **Name**: hier `Bloom` eintippen.
   - **URL** (teils "Remote MCP server URL"): hier die kopierte Adresse `https://service.envima.de/bloom/mcp`
     einfügen.
6. Falls das Fenster "Erweiterte Einstellungen" (Advanced) anbietet mit Feldern für "Client ID" oder "Client
   Secret": diese Felder **leer lassen**. Bloom braucht das nicht.
7. Auf **Hinzufügen** bzw. **Verbinden** klicken.
8. Jetzt öffnet sich die Bloom-Anmeldeseite in einem Fenster oder im Browser. Mit dem eigenen Bloom-Konto
   anmelden (Kundennummer, Benutzername und Passwort wie in Bloom selbst). Danach die Freigabe bestätigen.
9. Fertig. Claude zeigt die Verbindung **Bloom** jetzt als aktiv an.

Ab jetzt einfach im Chat fragen, siehe "Ausprobieren" weiter unten.

## Einrichten in ChatGPT

Bei ChatGPT muss man zuerst einmalig den Entwicklermodus anschalten, danach die Verbindung anlegen.

### Schritt A: Entwicklermodus anschalten (nur einmal nötig)

1. ChatGPT öffnen.
2. Oben oder unten auf das eigene Profilbild klicken, dann **Einstellungen** (Settings).
3. Auf **Apps & Connectors** gehen.
4. Ganz nach unten scrollen zu **Erweiterte Einstellungen** (Advanced settings).
5. Den Schalter **Entwicklermodus** (Developer mode) anschalten.

Hinweis: OpenAI verschiebt diesen Schalter manchmal. Findet man ihn dort nicht, unter **Einstellungen →
Sicherheit** (Security) nachsehen. In einem Firmen-Konto (Business oder Enterprise) muss ein Administrator den
Entwicklermodus zuerst erlauben.

### Schritt B: Die Bloom-Verbindung anlegen

1. Wieder zu **Einstellungen → Apps & Connectors** gehen.
2. Auf **Erstellen** bzw. **Create** klicken (teils "Add" oder ein Plus-Zeichen).
3. Die Felder ausfüllen:
   - **Name**: `Bloom`.
   - **Beschreibung** (Description): zum Beispiel `Ökobilanzen aus Bloom lesen und berechnen`.
   - **URL**: die kopierte Adresse `https://service.envima.de/bloom/mcp` einfügen.
   - **Authentifizierung** (Authentication): **OAuth** auswählen, falls gefragt wird.
4. Auf **Speichern** bzw. **Save** klicken.
5. Die Bloom-Anmeldeseite öffnet sich. Mit dem eigenen Bloom-Konto anmelden und die Freigabe bestätigen.
6. Fertig. Im Chat erscheint die Bloom-Verbindung jetzt als verfügbares Werkzeug.

## Einrichten in Claude Code (für Entwickler)

Wer Claude Code im Terminal nutzt, braucht die Adresse nicht von Hand, sondern installiert das fertige Plugin:

```
/plugin marketplace add envima-code/bloom-plugins
/plugin install bloom@envima
```

Danach einmal mit dem Bloom-Konto anmelden, wenn Claude Code danach fragt.

## Ausprobieren

Ist die Verbindung aktiv, einfach im Chat fragen. Beispiele:

- „Welche LCA-Modelle habe ich in Bloom?“
- „Berechne den CO2-Fußabdruck von Fitness Tracker (Demo) je Lebenszyklusphase.“
- „Welche Positionen verursachen die meisten Emissionen?“

Beim ersten Mal fragt Claude oder ChatGPT oft noch, ob das Bloom-Werkzeug benutzt werden darf. Das bestätigen.

## Was die Verbindung kann

| Werkzeug | Zweck |
|---|---|
| `list_models` | eigene LCA-Modelle auflisten |
| `get_model` | Phasen, Positionen, Mengen und Datenquellen eines Modells |
| `calculate_model` | CO2-Fußabdruck bzw. Wirkungskategorien je Phase, mit den größten Positionen |

Die Werkzeuge lesen nur, sie ändern nichts in Bloom. Die Zahlen rechnet Bloom selbst, nicht das Sprachmodell.

## Sicherheit

- Die Anmeldung läuft auf der Bloom-Seite. Das Passwort sieht weder Claude noch ChatGPT.
- Jede Person sieht nur ihre eigenen Modelle, auch nicht die von Kolleginnen und Kollegen im selben Konto.
- Ein Passwortwechsel in Bloom beendet die Verbindung sofort.

## Wenn etwas nicht klappt

- **"Verbindung fehlgeschlagen" oder es passiert nichts:** Fast immer die Adresse prüfen. Sie muss genau
  `https://service.envima.de/bloom/mcp` lauten, mit `/mcp` am Ende und ohne `-staging`.
- **"No access to the LCA module" oder keine Modelle:** Das Bloom-Konto hat das LCA-Modul nicht freigeschaltet.
  Bei envima freischalten lassen.
- **Der Connector-Knopf fehlt (Claude) oder der Entwicklermodus fehlt (ChatGPT):** Dann ist der Plan kostenlos
  oder eingeschränkt. Es braucht einen bezahlten Plan, bei Firmen-Konten zusätzlich die Freigabe durch einen
  Administrator.
- **"Model not found or no access":** Das Modell gehört jemand anderem. Über die Verbindung sieht man nur die
  eigenen Modelle.
- **Die Anmeldeseite öffnet sich nicht:** einmal abmelden, die Verbindung löschen und neu anlegen.

## Aufbau (für Entwickler)

| Datei | Für |
|---|---|
| `.claude-plugin/marketplace.json`, `plugins/bloom/.claude-plugin/plugin.json`, `plugins/bloom/.mcp.json` | Claude |
| `.agents/plugins/marketplace.json`, `plugins/bloom/plugin.json`, `plugins/bloom/mcp.json` | ChatGPT |
| `plugins/bloom/skills/bloom-lca/SKILL.md` | Hinweise für beide, wie die Werkzeuge zu nutzen sind |

Alle Dateien zeigen auf die Produktion `https://service.envima.de/bloom/mcp`.
