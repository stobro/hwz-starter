# PROMPTS: Kopierbare Prompts

Jeder Prompt wird so, wie er ist, in Claude Code eingefügt. «Wann» sagt, wann er dran ist. «Prüfen danach» sagt, was danach anzuschauen ist.

## Bau 1: die Liste

### 1. SPEC schreiben

```text
/spec Eine ToDo-App für mich: Aufgaben anlegen, abhaken und löschen.
```

- **Wann:** Ganz am Anfang, direkt nach `claude`.
- **Prüfen danach:** Die Fragen einzeln beantworten, den Look wählen. Dann docs/SPEC.md lesen: Stimmen Ziel, Look und die Kriterien unter «Fertig, wenn»? Freigeben mit «Passt, freigegeben.» oder sagen, was fehlt.

### 2. Plan machen

```text
/plan
```

- **Wann:** Nach der Freigabe der SPEC.
- **Prüfen danach:** docs/TASKS.md lesen. Höchstens 6 Tasks, jeder mit «Test zuerst». Freigeben mit «Plan freigegeben.»

### 3. Einen Task bauen (wiederholen)

```text
/task
```

- **Wann:** Nach der Freigabe des Plans. Immer wieder, bis alle Tasks in docs/TASKS.md `[x]` haben.
- **Prüfen danach:** Der Bericht nennt, was gebaut wurde und wo es zu sehen ist. Im Browser http://localhost:5173/hwz-todo/ öffnen und ausprobieren. Die letzte Zeile von `npm run check` muss grün sein.

### 4. Abnahme

```text
/review
```

- **Wann:** Wenn alle Tasks abgehakt sind.
- **Prüfen danach:** Die Tabelle durchgehen. Bei «Klick-Anleitung» selbst klicken und das Ergebnis melden. Bei Fehlern den vorgeschlagenen Fix-Prompt kopieren und senden.

### 5. Speichern

```text
/save Bau 1: Liste
```

- **Wann:** Nach bestandener Abnahme.
- **Prüfen danach:** Die Meldung zeigt den Commit und «gepusht». Das Repo auf github.com zeigt die neuen Dateien.

### 6. Veröffentlichen

```text
/publish
```

- **Wann:** Nach dem Speichern.
- **Prüfen danach:** Die URL `https://<user>.github.io/hwz-todo/` öffnen. Die App sieht gleich aus wie lokal. Bei 404: 2 Minuten warten, neu laden.

## Bau 2: das Board

### 7. Board-SPEC

```text
/spec Mach aus der Liste ein Board mit drei Spalten: Offen, In Arbeit, Erledigt.
```

- **Wann:** Nach Bau 1, wenn die Liste online ist.
- **Prüfen danach:** In docs/SPEC.md steht unter «## Features» ein neuer Abschnitt mit Gegeben/Wenn/Dann. Er erwähnt die Migration der gespeicherten Daten. Dann weiter mit `/plan`, `/task`, `/review`, `/save Bau 2: Board`, `/publish`.

### 8. Weitere Features

Fertige `/spec`-Prompts stehen in docs/FEATURES.md. Je Feature: `/spec …` → `/plan` → `/task` … → `/review` → `/save Bau 2: <Feature>` → `/publish`.

## Vier Sätze, die immer helfen

| Satz | Wann |
| ---- | ---- |
| «Ändere nur TaskCard.tsx, sonst nichts.» | Der Agent fasst zu viele Dateien an. Dateinamen anpassen. |
| «Schreib zuerst einen Test, der den Fehler zeigt, dann behebe ihn.» | Etwas funktioniert nicht wie erwartet. |
| «Stopp. Erklär in 3 Sätzen, wo es klemmt, und gib mir 2 Optionen.» | Der Agent dreht sich im Kreis. |
| «Zeig mir die letzte Zeile von npm run check.» | Der Agent sagt «fertig», aber es ist unklar, ob alles grün ist. |
