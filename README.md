# Abitur-Lernlandschaft – Informatik

Ein digitales Kanban-Board für selbstorganisierte Übungsphasen nach dem **Pull-Prinzip**: Schüler:innen entscheiden
selbst, welche Aufgabe sie als Nächstes bearbeiten, und schätzen dabei ihr eigenes Niveau ein – die Aufgaben sind
bewusst nicht nach Schwierigkeit beschriftet.

👉 **Live-Version ansehen:** sobald GitHub Pages aktiviert ist, erreichbar unter
`https://<dein-github-name>.github.io/<repository-name>/`

## Was ist enthalten?

| Datei | Zweck |
|---|---|
| `index.html` | Das Kanban-Board selbst – eine einzelne, eigenständige HTML-Datei ohne weitere Abhängigkeiten. |
| `Unterrichtskonzept_Lernlandschaft.docx` | Didaktisches Konzept: Grundprinzip, Stundenablauf, Rolle der Lehrkraft, Mehrwochen-Nutzung. |

Die drei vorbereiteten Themen-Blöcke (Wiederholung Schleifen & Verzweigungen, Arrays, Algorithmen – Sortieren &
Suchen) sind direkt aus den bestehenden interaktiven Werkstätten des Informatikunterrichts abgeleitet.

## Einrichtung auf GitHub Pages (einmalig, ca. 5 Minuten)

1. Ein neues Repository auf GitHub anlegen (öffentlich, damit Pages kostenlos funktioniert).
2. `index.html` (und optional diese README) in das Repository hochladen – z. B. per Drag & Drop im Browser unter
   „Add file → Upload files“.
3. Im Repository zu **Settings → Pages** wechseln.
4. Unter „Build and deployment“ als Quelle **Deploy from a branch** wählen, Branch `main` und Ordner `/ (root)`
   auswählen, dann **Save**.
5. Nach ein bis zwei Minuten ist die Seite unter der oben genannten Adresse erreichbar.

Jede spätere Änderung an `index.html` (z. B. neue Aufgaben) wird nach dem Hochladen automatisch innerhalb weniger
Minuten live übernommen – ein erneutes Aktivieren ist nicht nötig.

## Wie der Fortschritt gespeichert wird

Der Fortschritt jeder Schülerin/jedes Schülers wird **lokal im Browser** gespeichert (`localStorage`) – ohne
Anmeldung, ohne Server, ohne dass Daten das Gerät verlassen. Das bedeutet auch:

- Der Fortschritt ist an das jeweilige Gerät gebunden. Wer auf einem anderen Gerät weiterarbeitet, startet dort neu.
- Es gibt **keine automatische Zusammenführung** der Ergebnisse der ganzen Klasse. Ein Überblick entsteht über das
  gemeinsame Standup-Gespräch bzw. einen kurzen Blick auf die Bildschirme – siehe Konzeptdokument, Kapitel 9.3.
- Wird der Browser-Cache geleert oder ein privates/Inkognito-Fenster verwendet, geht der lokale Fortschritt verloren.

## Ein neues Thema ergänzen oder anpassen

Am Anfang des `<script>`-Bereichs in `index.html` befindet sich die Konstante `BLOCKS`. Jeder Block enthält:

```js
{
  id: "X",                 // kurze, eindeutige Kennung
  title: "Block X: ...",   // Überschrift, wie sie angezeigt wird
  weeks: "Wochen 9–10",    // reine Planungsangabe, rein informativ
  tasks: [
    { id: "X1", tier: 1, text: "Aufgabentext ..." },  // tier: 1=Basis, 2=Vertiefung, 3=Transfer
    ...
  ]
}
```

Einfach einen weiteren Block-Eintrag in die Liste einfügen (oder Aufgaben zu bestehenden Blöcken ergänzen) und die
Datei erneut hochladen – Fortschrittsanzeige, Speicherung und Lehrkraft-Ansicht funktionieren automatisch weiter.
Details und die didaktische Begründung dazu stehen im Unterrichtskonzept, Kapitel 5.

## Lizenz / Nutzung

Für den internen Schulgebrauch gedacht. Kein Tracking, keine externen Abhängigkeiten, keine Cookies außer der
lokalen Fortschrittsspeicherung im eigenen Browser.
