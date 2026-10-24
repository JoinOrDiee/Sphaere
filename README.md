# Sphäre

Die Meldungen und der Arbeitsstand der App — getrennt von ihr, damit sie sich
ändern können, **ohne dass jemand die App aktualisieren muss.**

Hier liegt nur, was ohnehin jeder Leser sieht. Kein Code, keine Kapitel.

## Die Dateien

| Datei | Was drinsteht | Wo es erscheint |
|---|---|---|
| `news.de.json` | die Meldungen | der News-Bereich |
| `workshop.de.json` | woran gerade gearbeitet wird | die Werkstatt in den News |

Eine japanische Fassung käme als `news.ja.json` daneben. Fehlt sie, gilt die
deutsche — das ist kein Fehler, sondern der Normalfall.

## Eine Meldung einspielen

1. Die Datei hier antippen, dann den **Stift** oben rechts.
2. Oben einen neuen Block einfügen — am einfachsten einen bestehenden kopieren
   und überschreiben. **Das Neueste steht oben.**
3. Unten auf **Commit changes** tippen.

Geht am Mac und am iPhone gleich, im Browser, ohne weitere Programme.

Beim Speichern prüft GitHub die Datei. **Ein grüner Haken heißt: alles heil.
Ein rotes Kreuz heißt: nicht hochgeladen lassen, sondern reparieren** — meist
ein Komma zu viel oder zu wenig.

## Wenn doch etwas kaputtgeht

Nichts Schlimmes: Die App nimmt eine unlesbare Datei gar nicht erst an. Sie
behält die letzte heile Fassung, und zur Not die aus dem App-Paket. Der Leser
merkt davon nichts.

Rückgängig machen geht über **History** oben rechts — jede frühere Fassung ist
noch da.

## Felder einer Meldung

```json
{
  "id": "news_007",
  "date": "2026-11-02",
  "tag": "Update",
  "title": "Die Überschrift",
  "imageId": null,
  "lede": "Der Vorspann, ein bis zwei Sätze.",
  "paras": ["Der erste Absatz.", "Der zweite."],
  "voice": "Eine Randnotiz von mir. Darf leer bleiben."
}
```

- **`id`** muss einmalig sein. Zwei Meldungen mit derselben kennen einander nicht.
- **`date`** immer `JJJJ-MM-TT`. Danach wird sortiert und nach Monaten gruppiert.
- **`tag`** ist das Schlagwort, nach dem sich filtern lässt.
- **`imageId`** zeigt auf ein Bild **im App-Paket**. Ein neues Bild braucht
  weiterhin eine neue App-Fassung; `null` heißt: kein Bild.
- **`voice`** ist freiwillig. Eine Randnotiz, die jede Meldung trüge, wäre keine.
