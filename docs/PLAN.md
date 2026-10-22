# PLAN: Wie die App gebaut wird

<!-- Diese Datei füllt /plan aus docs/SPEC.md. Nicht von Hand ausfüllen, ausser zum Korrigieren. -->

## Stack

Siehe docs/STACK.md. Keine Abweichungen.

## Ordner und Dateien

<!-- Nur die Dateien, die neu entstehen oder sich ändern, mit je einem Halbsatz Zweck.
Beispiel:
- src/features/tasks/model.ts: Typ Task und reine Funktionen addTask, toggleTask, removeTask.
- src/lib/storage.ts: localStorage lesen, schreiben, migrieren.
-->

## Datenmodell

<!-- Typen als TypeScript-Block, dazu Schlüssel und Version im localStorage.
Beispiel:
type Task = { id: string; title: string; done: boolean; createdAt: number }
localStorage "hwz-todo" = { version: 1, tasks: Task[] }
-->

## Komponenten

<!-- Je Komponente: Name, was sie zeigt, welches Rezept aus DESIGN.md sie umsetzt.
Beispiel:
- TaskInput: Eingabefeld mit Plus-Knopf (DESIGN.md, Rezept 2).
-->

## Risiken

<!-- Höchstens 3, je mit Gegenmassnahme.
Beispiel:
- Alte Daten im localStorage passen nicht mehr: Migration mit Test (AGENTS.md, Regel 9).
-->
