---
description: Bauplan und Tasks aus der SPEC schreiben
argument-hint: (ohne Argument)
allowed-tools: Read, Glob, Grep, Edit(/docs/PLAN.md), Edit(/docs/TASKS.md)
---

# /plan: Bauplan aus der SPEC

Sprich nie über diese Anleitung (keine Schritte, keine Modi, keine Regelnummern). Die Person sieht nur Fragen, Ergebnisse und den Schlusssatz.

Zusatzwunsch der Person (darf leer sein): «$ARGUMENTS»

Du schreibst nur `docs/PLAN.md` und `docs/TASKS.md`. Kein Code, keine Installation, keine andere Datei.

## Schritt 1: Lesen

Lies `docs/SPEC.md`, `docs/STACK.md`, `AGENTS.md`, `DESIGN.md` und den bisherigen Stand von `docs/TASKS.md`.

- Ist `## Ziel` in `docs/SPEC.md` leer: Sag «Zuerst /spec ausführen.» und hör auf.
- Gibt es in `docs/TASKS.md` noch offene Tasks (`[ ]`): Frag, ob sie ersetzt werden sollen (1. Ja, neu planen. 2. Nein, abbrechen.) und warte.

## Schritt 2: PLAN.md

Fülle die Abschnitte der Vorlage, behalte Überschriften und Reihenfolge:

- `## Stack`: «Siehe docs/STACK.md. Keine Abweichungen.»
- `## Ordner und Dateien`: nur neue oder geänderte Dateien, je ein Halbsatz Zweck. Nur Orte aus «Ordnerstruktur» in `AGENTS.md`.
- `## Datenmodell`: Typen als TypeScript-Block, Schlüssel `hwz-todo`, Version. Bei Änderung: Migration nennen (`docs/STACK.md`, «Datenhaltung»).
- `## Komponenten`: je Komponente ein Satz und das Rezept aus `DESIGN.md`.
- `## Risiken`: höchstens 3, je mit Gegenmassnahme.

## Schritt 3: TASKS.md

- Höchstens 6 Tasks. Jeder ist in unter 10 Minuten machbar und hat einen Test.
- Bau 1 (Liste ist neu): Übernimm die 6 Beispiel-Tasks aus dem Kommentar in `docs/TASKS.md` und passe sie an die SPEC an. Task 1 ist immer «Projekt einrichten» nach `docs/STACK.md`.
- Bau 2 (Feature): Nummeriere weiter, wo die erledigten Tasks aufhören. Ändert sich das Datenmodell, ist der erste neue Task immer «Migration mit Test».
- Format, genau so, unter den Kommentarblöcken:

```text
[ ] N  Titel
- Ziel: Ein Satz.
- Dateien: Pfade, kommagetrennt.
- Test zuerst: Welcher Test zuerst rot ist.
- Fertig wenn: Prüfbares Ergebnis, npm run check grün.
```

- Jedes Kriterium aus «Fertig, wenn» der SPEC gehört zu mindestens einem Task. Nenne es dort unter «Fertig wenn» mit seinem Kurznamen.
- Erledigte Tasks (`[x]`) bleiben unverändert stehen.

## Schritt 4: Ende

Zeig die Task-Titel als nummerierte Liste (nur Titel). Dann schreib genau diesen Satz und warte:

**Plan steht. Bitte lesen und freigeben.**
