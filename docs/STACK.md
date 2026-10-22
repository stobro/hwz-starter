# STACK.md: Technik und Einrichtung

Dieses Dokument ist die einzige Quelle für Technik, Versionen und Konfiguration. Der Agent kopiert die Inhalte wörtlich. Er ändert diese Datei nie ohne ausdrücklichen Auftrag (AGENTS.md, Regel 6).

## Stack in einem Satz je Teil

| Teil | Wozu |
| ---- | ---- |
| Vite | Startet die App lokal und baut sie für das Web (Build-Werkzeug). |
| React | Baut die Oberfläche aus Komponenten (wiederverwendbaren Bausteinen). |
| TypeScript (strict) | JavaScript mit Typen, findet Fehler vor dem Start. |
| Tailwind CSS v4 | Gestaltung direkt mit Klassen wie `bg-primary`, über `@tailwindcss/vite`. |
| shadcn/ui | Fertige, barrierefreie UI-Bausteine, die als Dateien im Projekt liegen. |
| motion | Animationen in React (früher Framer Motion). |
| @dnd-kit | Drag and Drop (Ziehen und Ablegen), erst in Bau 2. |
| sonner | Kurze Meldungen unten am Rand (Toasts), z. B. «Rückgängig». |
| canvas-confetti | Konfetti beim Abhaken. |
| lucide-react | Icons. |
| @fontsource-variable | Schriften lokal, ohne Google-Server (Datenschutz). |
| Vitest, Testing Library, jsdom | Automatische Tests, auch für Komponenten, ohne echten Browser. |
| ESLint (flat config), Prettier | Prüfen und formatieren den Code einheitlich. |

**Node:** mindestens 20.19 (`engines: ">=20.19"`). Empfohlen ist die aktuelle LTS-Version aus `.nvmrc` (24.22.1).

**Versionen:** Alle Versionen sind exakt gepinnt (kein `^`, kein `~`). Ermittelt mit `npm view <paket> version` am 22. Oktober 2026.
Ausnahmen mit Grund: `typescript` 6.0.3 statt 7.x (typescript-eslint unterstützt nur bis 6.0), `vitest` 4.1.12 und `jsdom` 29.1.1 statt 5.x/30.x (die neuen Versionen verlangen Node 22 oder 24 und brechen `>=20.19`).

## Erlaubt-Liste

Genau diese Pakete in genau diesen Versionen. Alles andere nur nach Rückfrage (AGENTS.md, Regel 5).

| Paket | Version | Art | Wozu |
| ----- | ------- | --- | ---- |
| `@dnd-kit/core` | 6.3.1 | App | Drag and Drop (Bau 2) |
| `@dnd-kit/sortable` | 10.0.0 | App | Sortieren per Drag and Drop (Bau 2) |
| `@dnd-kit/utilities` | 3.2.2 | App | Hilfen für dnd-kit (CSS-Transform) |
| `@fontsource-variable/fredoka` | 5.3.0 | App | Schrift Candy (Überschrift) |
| `@fontsource-variable/inter` | 5.3.0 | App | Schrift Aurora (Text) |
| `@fontsource-variable/jetbrains-mono` | 5.3.0 | App | Mono-Schrift (Zahlen, Neon-Akzente) |
| `@fontsource-variable/nunito` | 5.3.0 | App | Schrift Candy (Text) |
| `@fontsource-variable/outfit` | 5.3.0 | App | Schrift Aurora (Überschrift) |
| `@fontsource-variable/space-grotesk` | 5.3.0 | App | Schrift Neon |
| `canvas-confetti` | 1.9.4 | App | Konfetti |
| `class-variance-authority` | 0.7.1 | App | Varianten für shadcn-Bausteine |
| `cn` | 0.5.0 | App | Klassen zusammenführen (cn(), von shadcn genutzt) |
| `lucide-react` | 1.61.0 | App | Icons |
| `motion` | 14.5.0 | App | Animationen |
| `next-themes` | 0.4.6 | App | von der shadcn-Sonner-Komponente verlangt |
| `radix-ui` | 1.8.1 | App | Grundlage der shadcn-Bausteine |
| `react` | 19.3.1 | App | Oberfläche |
| `react-dom` | 19.3.1 | App | React im Browser |
| `sonner` | 2.0.8 | App | Toasts |
| `@eslint/js` | 10.0.1 | Entwicklung | ESLint-Grundregeln |
| `@tailwindcss/vite` | 4.3.3 | Entwicklung | Tailwind in Vite |
| `@testing-library/dom` | 10.4.2 | Entwicklung | Testing Library (Basis) |
| `@testing-library/jest-dom` | 7.0.1 | Entwicklung | Zusätzliche Test-Prüfungen wie toBeVisible |
| `@testing-library/react` | 16.3.3 | Entwicklung | React-Komponenten testen |
| `@testing-library/user-event` | 14.6.8 | Entwicklung | Klicks und Tippen im Test |
| `@types/canvas-confetti` | 1.9.0 | Entwicklung | Typen für canvas-confetti |
| `@types/node` | 24.19.2 | Entwicklung | Typen für Node (vite.config.ts) |
| `@types/react` | 19.3.0 | Entwicklung | Typen für React |
| `@types/react-dom` | 19.3.0 | Entwicklung | Typen für React DOM |
| `@vitejs/plugin-react` | 6.1.2 | Entwicklung | React in Vite |
| `eslint` | 10.13.0 | Entwicklung | Code prüfen |
| `eslint-plugin-react-hooks` | 7.1.1 | Entwicklung | Regeln für React-Hooks |
| `eslint-plugin-react-refresh` | 0.5.7 | Entwicklung | Regeln für schnelles Neuladen |
| `globals` | 17.13.0 | Entwicklung | Browser-Globale für ESLint |
| `jsdom` | 29.1.1 | Entwicklung | Browser-Ersatz für Tests |
| `prettier` | 3.9.10 | Entwicklung | Formatieren |
| `shadcn` | 4.22.1 | Entwicklung | CLI für shadcn/ui (npx shadcn add) |
| `tailwindcss` | 4.3.3 | Entwicklung | Tailwind CSS |
| `tw-animate-css` | 1.4.0 | Entwicklung | Animationen für shadcn-Bausteine |
| `typescript` | 6.0.3 | Entwicklung | TypeScript |
| `typescript-eslint` | 8.72.0 | Entwicklung | ESLint für TypeScript |
| `vite` | 8.3.5 | Entwicklung | Build-Werkzeug |
| `vitest` | 4.1.12 | Entwicklung | Test-Runner |

Zur Installation eines dieser Pakete (falls es fehlt) immer mit Version: `npm install <paket>@<version>`.

## shadcn/ui-Bausteine

Task 1 installiert genau diese: `button`, `input`, `card`, `checkbox`, `badge`, `dialog`, `dropdown-menu`, `tooltip`, `progress`, `separator`, `sonner`.
Sie liegen danach in `src/components/ui/`. Weitere nur nach Rückfrage, dann mit `npx shadcn add <name> --yes`.
Die Dateien in `src/components/ui/` werden nicht von Hand umgeschrieben. Anpassungen passieren über Klassen beim Verwenden.

## Datenhaltung

- Speicher: `localStorage` (Speicher im Browser, bleibt nach dem Neuladen).
- Schlüssel: `"hwz-todo"`.
- Format: `{ version: number, tasks: Task[] }`.
- Bau 1, `version: 1`:

  ```ts
  export type Task = {
    id: string // crypto.randomUUID()
    title: string // getrimmt, 1 bis 200 Zeichen
    done: boolean
    createdAt: number // Date.now()
  }
  ```

- Lesen (`loadState`): fehlt der Schlüssel oder ist der Inhalt kaputt (kein JSON, falsche Form), gibt die Funktion `{ version: CURRENT_VERSION, tasks: [] }` zurück und wirft keinen Fehler. Eine ältere Version wird migriert.
- Schreiben (`saveState`): nach jeder Änderung den ganzen Zustand speichern.
- Alles in `src/lib/storage.ts`, getestet in `src/lib/storage.test.ts`.
- **Hinweis für Bau 2:** `status: 'todo' | 'doing' | 'done'` ersetzt `done`. Dafür `CURRENT_VERSION = 2` und eine Migration `migrateV1toV2`: `done: true` → `status: 'done'`, `done: false` → `status: 'todo'`. Die Migration hat einen eigenen Test mit echten Daten im Format von Version 1. Gespeicherte Aufgaben gehen nie verloren (AGENTS.md, Regel 9).

## Skripte

| Skript | Befehl | Wozu |
| ------ | ------ | ---- |
| `dev` | `vite` | App lokal starten: http://localhost:5173/hwz-todo/ |
| `build` | `vite build` | App für das Web bauen (Ordner `dist/`) |
| `preview` | `vite preview` | Gebaute App lokal ansehen |
| `test` | `vitest` | Tests im Beobachtungsmodus; einmalig: `npm run test -- --run` |
| `lint` | `eslint .` | Code-Regeln prüfen |
| `typecheck` | `tsc -b --noEmit` | Typen prüfen |
| `format` | `prettier --write .` | Code einheitlich formatieren |
| `check` | `npm run typecheck && npm run lint && npm run test -- --run && npm run build` | Alles zusammen. Grün heisst fertig. |

---

## Task 1: Projekt einrichten

Diese Schritte laufen ohne jede Rückfrage. Keine interaktiven Prompts. Der Agent führt sie der Reihe nach aus und erstellt die Dateien mit genau dem Inhalt unten. Er ändert nichts daran.

1. **Node prüfen:** `node -v`. Die Version muss 20.19 oder höher sein. Sonst stopp und der Person sagen: «Bitte Node 24 LTS von nodejs.org installieren.»
2. **Dateien anlegen:** Alle Dateien aus «Dateien für Task 1» unten mit exakt diesem Inhalt erstellen: `package.json`, `.npmrc`, `.prettierrc`, `.prettierignore`, `vite.config.ts`, `tsconfig.json`, `tsconfig.app.json`, `tsconfig.node.json`, `eslint.config.js`, `vitest.setup.ts`, `components.json`, `index.html`, `src/index.css`, `src/lib/utils.ts`, `src/main.tsx`, `src/App.tsx`, `src/App.test.tsx`.
3. **Look setzen:** In `index.html` den Wert von `data-look` auf den Look aus docs/SPEC.md setzen (`aurora`, `candy` oder `neon`). Steht dort nichts, bleibt `aurora`.
4. **Pakete installieren:** `npm install --no-audit --no-fund`. Das erzeugt `package-lock.json`. Diese Datei gehört ins Repo (die Veröffentlichung braucht sie).
5. **shadcn-Bausteine holen:** `npx shadcn add button input card checkbox badge dialog dropdown-menu tooltip progress separator sonner --yes --silent`.
   Bricht der Befehl mit «Connect Timeout» ab, einfach genau gleich noch einmal ausführen (der Server von shadcn ist manchmal langsam).
6. **Prüfen, dass nichts dazukam:** `package.json` muss noch genau den Inhalt von unten haben. Hat shadcn ein Paket ergänzt, stopp und die Person fragen (AGENTS.md, Regel 5).
7. **Check:** `npm run check`. Er muss grün sein. Die letzte Zeile lautet `✓ built in …`.
8. **Ansehen:** Dev-Server im Hintergrund starten (`npm run dev`) und der Person die Adresse http://localhost:5173/hwz-todo/ nennen.
9. **Abhaken:** In docs/TASKS.md Task 1 auf `[x]` setzen.

Hinweis für den Test-zuerst-Grundsatz: In Task 1 ist der Test `src/App.test.tsx` gleich dabei, weil es vorher keinen Code gibt, der rot sein könnte.

## Dateien für Task 1


### `package.json`

```json
{
  "name": "hwz-todo",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "engines": {
    "node": ">=20.19"
  },
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "test": "vitest",
    "lint": "eslint .",
    "typecheck": "tsc -b --noEmit",
    "format": "prettier --write .",
    "check": "npm run typecheck && npm run lint && npm run test -- --run && npm run build"
  },
  "dependencies": {
    "@dnd-kit/core": "6.3.1",
    "@dnd-kit/sortable": "10.0.0",
    "@dnd-kit/utilities": "3.2.2",
    "@fontsource-variable/fredoka": "5.3.0",
    "@fontsource-variable/inter": "5.3.0",
    "@fontsource-variable/jetbrains-mono": "5.3.0",
    "@fontsource-variable/nunito": "5.3.0",
    "@fontsource-variable/outfit": "5.3.0",
    "@fontsource-variable/space-grotesk": "5.3.0",
    "canvas-confetti": "1.9.4",
    "class-variance-authority": "0.7.1",
    "cn": "0.5.0",
    "lucide-react": "1.61.0",
    "motion": "14.5.0",
    "next-themes": "0.4.6",
    "radix-ui": "1.8.1",
    "react": "19.3.1",
    "react-dom": "19.3.1",
    "sonner": "2.0.8"
  },
  "devDependencies": {
    "@eslint/js": "10.0.1",
    "@tailwindcss/vite": "4.3.3",
    "@testing-library/dom": "10.4.2",
    "@testing-library/jest-dom": "7.0.1",
    "@testing-library/react": "16.3.3",
    "@testing-library/user-event": "14.6.8",
    "@types/canvas-confetti": "1.9.0",
    "@types/node": "24.19.2",
    "@types/react": "19.3.0",
    "@types/react-dom": "19.3.0",
    "@vitejs/plugin-react": "6.1.2",
    "eslint": "10.13.0",
    "eslint-plugin-react-hooks": "7.1.1",
    "eslint-plugin-react-refresh": "0.5.7",
    "globals": "17.13.0",
    "jsdom": "29.1.1",
    "prettier": "3.9.10",
    "shadcn": "4.22.1",
    "tailwindcss": "4.3.3",
    "tw-animate-css": "1.4.0",
    "typescript": "6.0.3",
    "typescript-eslint": "8.72.0",
    "vite": "8.3.5",
    "vitest": "4.1.12"
  }
}
```

### `.npmrc`

```ini
save-exact=true
```

### `.prettierrc`

```json
{
  "semi": false,
  "singleQuote": true,
  "trailingComma": "all",
  "printWidth": 100
}
```

### `.prettierignore`

```text
dist
node_modules
package-lock.json
src/components/ui
*.md
.claude
.github
```

### `vite.config.ts`

```ts
/// <reference types="vitest/config" />
import path from 'node:path'
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  base: process.env.VITE_BASE ?? '/hwz-todo/',
  plugins: [react(), tailwindcss()],
  resolve: {
    alias: { '@': path.resolve(import.meta.dirname, './src') },
  },
  server: { port: 5173, strictPort: true },
  test: {
    globals: true,
    environment: 'jsdom',
    setupFiles: ['./vitest.setup.ts'],
    css: true,
  },
})
```

### `tsconfig.json`

```json
{
  "files": [],
  "references": [{ "path": "./tsconfig.app.json" }, { "path": "./tsconfig.node.json" }],
  "compilerOptions": {
    "paths": { "@/*": ["./src/*"] }
  }
}
```

### `tsconfig.app.json`

```json
{
  "compilerOptions": {
    "tsBuildInfoFile": "./node_modules/.tmp/tsconfig.app.tsbuildinfo",
    "target": "ES2022",
    "lib": ["ES2022", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "types": ["vite/client", "vitest/globals", "@testing-library/jest-dom"],
    "skipLibCheck": true,
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "verbatimModuleSyntax": true,
    "moduleDetection": "force",
    "noEmit": true,
    "jsx": "react-jsx",
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true,
    "noUncheckedSideEffectImports": true,
    "paths": { "@/*": ["./src/*"] }
  },
  "include": ["src", "vitest.setup.ts"]
}
```

### `tsconfig.node.json`

```json
{
  "compilerOptions": {
    "tsBuildInfoFile": "./node_modules/.tmp/tsconfig.node.tsbuildinfo",
    "target": "ES2023",
    "lib": ["ES2023"],
    "module": "ESNext",
    "types": ["node"],
    "skipLibCheck": true,
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "verbatimModuleSyntax": true,
    "moduleDetection": "force",
    "noEmit": true,
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
  },
  "include": ["vite.config.ts"]
}
```

### `eslint.config.js`

```js
import js from '@eslint/js'
import globals from 'globals'
import reactHooks from 'eslint-plugin-react-hooks'
import reactRefresh from 'eslint-plugin-react-refresh'
import tseslint from 'typescript-eslint'
import { defineConfig, globalIgnores } from 'eslint/config'

export default defineConfig([
  globalIgnores(['dist', 'coverage', 'node_modules']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      js.configs.recommended,
      tseslint.configs.recommended,
      reactHooks.configs.flat['recommended-latest'],
      reactRefresh.configs.vite,
    ],
    languageOptions: {
      ecmaVersion: 2022,
      globals: globals.browser,
    },
  },
  {
    files: ['src/components/ui/**/*.{ts,tsx}'],
    rules: { 'react-refresh/only-export-components': 'off' },
  },
])
```

### `vitest.setup.ts`

```ts
import '@testing-library/jest-dom/vitest'
import { cleanup } from '@testing-library/react'
import { afterEach, vi } from 'vitest'

// jsdom kennt diese Browser-Funktionen nicht. sonner, motion und Radix brauchen sie.
Object.defineProperty(window, 'matchMedia', {
  writable: true,
  value: vi.fn((query: string) => ({
    matches: false,
    media: query,
    onchange: null,
    addListener: vi.fn(),
    removeListener: vi.fn(),
    addEventListener: vi.fn(),
    removeEventListener: vi.fn(),
    dispatchEvent: vi.fn(),
  })),
})

class ResizeObserverMock {
  observe() {}
  unobserve() {}
  disconnect() {}
}
globalThis.ResizeObserver = ResizeObserverMock as unknown as typeof ResizeObserver

class IntersectionObserverMock {
  readonly root = null
  readonly rootMargin = ''
  readonly thresholds = []
  observe() {}
  unobserve() {}
  disconnect() {}
  takeRecords() {
    return []
  }
}
globalThis.IntersectionObserver = IntersectionObserverMock as unknown as typeof IntersectionObserver

Element.prototype.scrollIntoView = vi.fn()
HTMLCanvasElement.prototype.getContext = vi.fn(() => null) as unknown as typeof HTMLCanvasElement.prototype.getContext

afterEach(() => {
  cleanup()
  localStorage.clear()
})
```

### `components.json`

```json
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "rsc": false,
  "tsx": true,
  "tailwind": {
    "config": "",
    "css": "src/index.css",
    "baseColor": "neutral",
    "cssVariables": true,
    "prefix": ""
  },
  "iconLibrary": "lucide",
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils",
    "ui": "@/components/ui",
    "lib": "@/lib",
    "hooks": "@/hooks"
  }
}
```

### `index.html`

```html
<!doctype html>
<html lang="de-CH" data-look="aurora">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>✅</text></svg>" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="color-scheme" content="dark light" />
    <title>Meine Aufgaben</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
```

### `src/lib/utils.ts`

```ts
export { cn } from 'cn'
```

### `src/main.tsx`

```tsx
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App'

createRoot(document.getElementById('root')!).render(
  <StrictMode>
    <App />
  </StrictMode>,
)
```

### `src/App.tsx`

```tsx
import { MotionConfig } from 'motion/react'
import { Toaster } from '@/components/ui/sonner'
import { TooltipProvider } from '@/components/ui/tooltip'

export default function App() {
  return (
    <MotionConfig reducedMotion="user">
      <TooltipProvider>
        <main className="mx-auto flex min-h-dvh w-full max-w-3xl flex-col gap-8 px-4 py-10 sm:px-6 sm:py-16">
          <header className="flex flex-col gap-2">
            <h1 className="text-gradient text-5xl font-bold tracking-tight sm:text-6xl">Meine Aufgaben</h1>
            <p className="text-muted-foreground">Hier entsteht die App.</p>
          </header>
        </main>
        <Toaster position="bottom-center" richColors closeButton />
      </TooltipProvider>
    </MotionConfig>
  )
}
```

### `src/App.test.tsx`

```tsx
import { render, screen } from '@testing-library/react'
import { describe, expect, it } from 'vitest'
import App from './App'

describe('App', () => {
  it('shows the hero title', () => {
    render(<App />)
    expect(screen.getByRole('heading', { level: 1 })).toBeInTheDocument()
  })

  it.each(['aurora', 'candy', 'neon'])('renders with look %s', (look) => {
    document.documentElement.dataset.look = look
    render(<App />)
    expect(document.documentElement).toHaveAttribute('data-look', look)
    expect(screen.getByRole('heading', { level: 1 })).toBeVisible()
  })
})
```

### `src/index.css`

```css
/* ==========================================================================
   hwz-todo – globale Styles
   Tailwind v4 + shadcn/ui + drei Looks (aurora, candy, neon).
   Der Look kommt aus <html data-look="...">. Ohne Attribut gilt aurora.
   Quelle aller Werte: DESIGN.md. Hier nichts erfinden, nur von dort kopieren.
   ========================================================================== */

@import 'tailwindcss';
@import 'tw-animate-css';

/* Schriften lokal über Fontsource (keine Google-CDN) */
@import '@fontsource-variable/outfit';
@import '@fontsource-variable/inter';
@import '@fontsource-variable/fredoka';
@import '@fontsource-variable/nunito';
@import '@fontsource-variable/space-grotesk';
@import '@fontsource-variable/jetbrains-mono';

/* shadcn nutzt «dark:» – aurora und neon sind dunkle Looks */
@custom-variant dark (&:where([data-look='aurora'], [data-look='aurora'] *, [data-look='neon'], [data-look='neon'] *));

/* --------------------------------------------------------------------------
   Theme: Farben als Tailwind-Klassen (bg-primary, text-muted-foreground …)
   -------------------------------------------------------------------------- */
@theme inline {
  --color-background: var(--background);
  --color-foreground: var(--foreground);
  --color-card: var(--card);
  --color-card-foreground: var(--card-foreground);
  --color-popover: var(--popover);
  --color-popover-foreground: var(--popover-foreground);
  --color-primary: var(--primary);
  --color-primary-foreground: var(--primary-foreground);
  --color-secondary: var(--secondary);
  --color-secondary-foreground: var(--secondary-foreground);
  --color-muted: var(--muted);
  --color-muted-foreground: var(--muted-foreground);
  --color-accent: var(--accent);
  --color-accent-foreground: var(--accent-foreground);
  --color-destructive: var(--destructive);
  --color-destructive-foreground: var(--destructive-foreground);
  --color-success: var(--success);
  --color-border: var(--border);
  --color-input: var(--input);
  --color-ring: var(--ring);
  --color-chart-1: var(--chart-1);
  --color-chart-2: var(--chart-2);
  --color-chart-3: var(--chart-3);
  --color-chart-4: var(--chart-4);
  --color-chart-5: var(--chart-5);
  --radius-sm: calc(var(--radius) - 4px);
  --radius-md: calc(var(--radius) - 2px);
  --radius-lg: var(--radius);
  --radius-xl: calc(var(--radius) + 4px);
  --radius-2xl: calc(var(--radius) + 10px);
}

/* --------------------------------------------------------------------------
   Theme: Schriften, Schatten, Blur, Bewegung (Standard = aurora).
   Jeder Look überschreibt diese Werte weiter unten.
   Klassen: font-heading, font-sans, font-mono, shadow-card, shadow-pop,
   backdrop-blur-glass, ease-spring, ease-out-soft, animate-shake …
   -------------------------------------------------------------------------- */
@theme {
  --font-heading: 'Outfit Variable', ui-sans-serif, system-ui, sans-serif;
  --font-sans: 'Inter Variable', ui-sans-serif, system-ui, sans-serif;
  --font-mono: 'JetBrains Mono Variable', ui-monospace, monospace;

  --shadow-card: 0 1px 0 0 rgb(255 255 255 / 0.08) inset, 0 12px 32px -12px rgb(8 6 30 / 0.7);
  --shadow-pop: 0 1px 0 0 rgb(255 255 255 / 0.12) inset, 0 24px 48px -16px rgb(47 224 194 / 0.35);
  --blur-glass: 18px;

  --ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);
  --ease-out-soft: cubic-bezier(0.22, 1, 0.36, 1);

  --animate-shake: shake 0.4s var(--ease-out-soft);
  --animate-pop: pop 0.35s var(--ease-spring);
  --animate-mesh: mesh 24s ease-in-out infinite alternate;

  @keyframes shake {
    0%, 100% { transform: translateX(0); }
    20% { transform: translateX(-6px); }
    40% { transform: translateX(6px); }
    60% { transform: translateX(-4px); }
    80% { transform: translateX(4px); }
  }
  @keyframes pop {
    0% { transform: scale(0.6); }
    60% { transform: scale(1.15); }
    100% { transform: scale(1); }
  }
  @keyframes mesh {
    0% { transform: translate3d(0, 0, 0) rotate(0deg) scale(1); }
    50% { transform: translate3d(-4%, 3%, 0) rotate(8deg) scale(1.08); }
    100% { transform: translate3d(3%, -4%, 0) rotate(-6deg) scale(1.04); }
  }
}

/* ==========================================================================
   LOOK 1: AURORA (Standard)
   ========================================================================== */
:root,
[data-look='aurora'] {
  color-scheme: dark;
  --radius: 1rem;

  --background: #0c0a24;
  --foreground: #f5f3ff;
  --card: rgb(30 26 74 / 0.62);
  --card-foreground: #f5f3ff;
  --popover: #1a1640;
  --popover-foreground: #f5f3ff;
  --primary: #6d4cf0;
  --primary-foreground: #ffffff;
  --secondary: #2b2566;
  --secondary-foreground: #f5f3ff;
  --muted: #1a1640;
  --muted-foreground: #b9b3e6;
  --accent: #2fe0c2;
  --accent-foreground: #062824;
  --destructive: #d9264f;
  --destructive-foreground: #ffffff;
  --success: #2fe0c2;
  --border: rgb(196 181 253 / 0.18);
  --input: rgb(196 181 253 / 0.24);
  --ring: #2fe0c2;
  --chart-1: #6d4cf0;
  --chart-2: #2fe0c2;
  --chart-3: #f0abfc;
  --chart-4: #c4b5fd;
  --chart-5: #38bdf8;

  --gradient-hero: linear-gradient(100deg, #c4b5fd 0%, #2fe0c2 45%, #f0abfc 100%);
  --gradient-card: linear-gradient(145deg, rgb(255 255 255 / 0.10) 0%, rgb(255 255 255 / 0.02) 60%);
  --gradient-mesh:
    radial-gradient(40% 50% at 20% 20%, rgb(47 224 194 / 0.35) 0%, transparent 70%),
    radial-gradient(45% 55% at 80% 10%, rgb(109 76 240 / 0.45) 0%, transparent 70%),
    radial-gradient(50% 60% at 70% 90%, rgb(240 171 252 / 0.25) 0%, transparent 70%),
    radial-gradient(60% 60% at 10% 90%, rgb(56 189 248 / 0.20) 0%, transparent 70%);
  --glow: 0 0 0 1px rgb(47 224 194 / 0.45), 0 0 24px 2px rgb(47 224 194 / 0.35);
  --confetti: #2fe0c2, #c4b5fd, #f0abfc, #6d4cf0;

  --duration-fast: 150ms;
  --duration-base: 250ms;
  --duration-slow: 450ms;
}

/* ==========================================================================
   LOOK 2: CANDY
   ========================================================================== */
[data-look='candy'] {
  color-scheme: light;
  --radius: 1.5rem;

  --background: #fff6fb;
  --foreground: #3a1748;
  --card: rgb(255 255 255 / 0.88);
  --card-foreground: #3a1748;
  --popover: #ffffff;
  --popover-foreground: #3a1748;
  --primary: #d6247e;
  --primary-foreground: #ffffff;
  --secondary: #fff1a8;
  --secondary-foreground: #3a1748;
  --muted: #fbe7f3;
  --muted-foreground: #75507f;
  --accent: #9ef0cf;
  --accent-foreground: #3a1748;
  --destructive: #c8213f;
  --destructive-foreground: #ffffff;
  --success: #0a6249;
  --border: #f3c6e0;
  --input: #ebb4d4;
  --ring: #9333ea;
  --chart-1: #d6247e;
  --chart-2: #9ef0cf;
  --chart-3: #fff1a8;
  --chart-4: #dcc6ff;
  --chart-5: #ff9ecd;

  --gradient-hero: linear-gradient(100deg, #a3105a 0%, #7322b8 50%, #0a6249 100%);
  --gradient-card: linear-gradient(145deg, #ffffff 0%, #fff4fa 100%);
  --gradient-mesh:
    radial-gradient(40% 50% at 15% 15%, rgb(255 158 205 / 0.55) 0%, transparent 70%),
    radial-gradient(45% 55% at 85% 10%, rgb(255 241 168 / 0.70) 0%, transparent 70%),
    radial-gradient(50% 60% at 80% 85%, rgb(158 240 207 / 0.55) 0%, transparent 70%),
    radial-gradient(55% 60% at 10% 90%, rgb(220 198 255 / 0.55) 0%, transparent 70%);
  --glow: 0 0 0 3px #ffffff, 0 0 0 6px rgb(214 36 126 / 0.45);
  --confetti: #ff9ecd, #fff1a8, #9ef0cf, #dcc6ff, #d6247e;

  --font-heading: 'Fredoka Variable', ui-rounded, system-ui, sans-serif;
  --font-sans: 'Nunito Variable', ui-rounded, system-ui, sans-serif;
  --shadow-card: 0 6px 0 0 #f3c6e0, 0 14px 28px -10px rgb(214 36 126 / 0.30);
  --shadow-pop: 0 8px 0 0 #9ef0cf, 0 22px 40px -12px rgb(115 34 184 / 0.35);
  --blur-glass: 8px;
  --ease-spring: cubic-bezier(0.3, 1.8, 0.5, 1);

  --duration-fast: 160ms;
  --duration-base: 280ms;
  --duration-slow: 520ms;
}

/* ==========================================================================
   LOOK 3: NEON
   ========================================================================== */
[data-look='neon'] {
  color-scheme: dark;
  --radius: 0.5rem;

  --background: #07060f;
  --foreground: #e6fbff;
  --card: rgb(18 15 34 / 0.78);
  --card-foreground: #e6fbff;
  --popover: #120f22;
  --popover-foreground: #e6fbff;
  --primary: #00e5ff;
  --primary-foreground: #001619;
  --secondary: #1f1a3a;
  --secondary-foreground: #e6fbff;
  --muted: #120f22;
  --muted-foreground: #9aa6c8;
  --accent: #ff3dd8;
  --accent-foreground: #1d0019;
  --destructive: #e0244e;
  --destructive-foreground: #ffffff;
  --success: #b4ff39;
  --border: rgb(0 229 255 / 0.28);
  --input: rgb(0 229 255 / 0.35);
  --ring: #00e5ff;
  --chart-1: #00e5ff;
  --chart-2: #ff3dd8;
  --chart-3: #b4ff39;
  --chart-4: #8b5cf6;
  --chart-5: #ffb800;

  --gradient-hero: linear-gradient(100deg, #00e5ff 0%, #ff3dd8 55%, #b4ff39 100%);
  --gradient-card: linear-gradient(145deg, rgb(0 229 255 / 0.06) 0%, rgb(255 61 216 / 0.04) 100%);
  --gradient-mesh:
    radial-gradient(35% 45% at 15% 20%, rgb(0 229 255 / 0.22) 0%, transparent 70%),
    radial-gradient(40% 50% at 85% 15%, rgb(255 61 216 / 0.22) 0%, transparent 70%),
    radial-gradient(45% 55% at 60% 95%, rgb(139 92 246 / 0.20) 0%, transparent 70%);
  --glow: 0 0 0 1px rgb(0 229 255 / 0.7), 0 0 16px 1px rgb(0 229 255 / 0.55), 0 0 40px 4px rgb(255 61 216 / 0.25);
  --confetti: #00e5ff, #ff3dd8, #b4ff39, #ffffff;

  --font-heading: 'Space Grotesk Variable', ui-sans-serif, system-ui, sans-serif;
  --font-sans: 'Space Grotesk Variable', ui-sans-serif, system-ui, sans-serif;
  --font-mono: 'JetBrains Mono Variable', ui-monospace, monospace;
  --shadow-card: 0 0 0 1px rgb(0 229 255 / 0.25), 0 10px 30px -12px rgb(0 0 0 / 0.9);
  --shadow-pop: 0 0 0 1px rgb(255 61 216 / 0.6), 0 0 28px 2px rgb(255 61 216 / 0.35);
  --blur-glass: 10px;
  --ease-spring: cubic-bezier(0.5, 1.6, 0.4, 1);

  --duration-fast: 120ms;
  --duration-base: 200ms;
  --duration-slow: 380ms;
}

/* ==========================================================================
   Basis
   ========================================================================== */
@layer base {
  * {
    @apply border-border outline-ring/50;
  }
  html {
    -webkit-text-size-adjust: 100%;
  }
  body {
    @apply min-h-dvh bg-background font-sans text-foreground antialiased;
    position: relative;
    isolation: isolate;
  }
  h1, h2, h3 {
    @apply font-heading;
  }

  /* Animierter Mesh-Hintergrund (reines CSS) */
  body::before {
    content: '';
    position: fixed;
    inset: -20%;
    z-index: -2;
    pointer-events: none;
    background: var(--gradient-mesh);
    filter: blur(40px);
    animation: var(--animate-mesh);
    will-change: transform;
  }

  /* Neon: Hauch von Scanlines */
  [data-look='neon'] body::after {
    content: '';
    position: fixed;
    inset: 0;
    z-index: -1;
    pointer-events: none;
    background: repeating-linear-gradient(to bottom, rgb(255 255 255 / 0.035) 0 1px, transparent 1px 3px);
  }

  /* Sichtbarer Fokus im Look */
  :focus-visible {
    outline: 2px solid var(--ring);
    outline-offset: 2px;
  }

  /* Bewegung reduzieren, wenn das System es verlangt */
  @media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
      animation-duration: 0.01ms !important;
      animation-iteration-count: 1 !important;
      transition-duration: 0.01ms !important;
      scroll-behavior: auto !important;
    }
    body::before {
      animation: none !important;
    }
  }
}

/* ==========================================================================
   Eigene Klassen für die Rezepte in DESIGN.md
   ========================================================================== */

/* Verlaufstext für die Hero-Überschrift */
@utility text-gradient {
  background-image: var(--gradient-hero);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
}

/* Milchglas-Fläche für Karten und Spalten */
@utility glass {
  background-color: var(--card);
  background-image: var(--gradient-card);
  backdrop-filter: blur(var(--blur-glass)) saturate(140%);
  -webkit-backdrop-filter: blur(var(--blur-glass)) saturate(140%);
}

/* Leuchtender Rand (Hover, Drop-Bereich, aktive Spalte) */
@utility glow {
  box-shadow: var(--glow);
}

/* Verlauf als Fläche (z. B. Fortschrittsring, Badges) */
@utility bg-gradient-hero {
  background-image: var(--gradient-hero);
}

/* Übergänge mit Look-Tempo */
@utility transition-look {
  transition-property: transform, box-shadow, background-color, border-color, color, opacity;
  transition-duration: var(--duration-base);
  transition-timing-function: var(--ease-out-soft);
}
```
