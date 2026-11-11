# Calculator

A clean, responsive calculator web app built with **SvelteKit**, **TypeScript** and **Tailwind CSS**. The interface title is in Arabic (آلة حاسبة).

## Features

- Basic operations: addition, subtraction, multiplication, division and percentage
- Decimal numbers, clear (`C`) and delete (`Del`) buttons
- Full keyboard support: press the key that matches a button
- Click sound on every button press
- The display flashes red when an expression is invalid

## Tech stack

SvelteKit 2, Svelte 4, TypeScript, Tailwind CSS, Vite.

## Getting started

Requirements: Node.js 18 or newer.

```bash
git clone https://github.com/IMawaddah/calculator.git
cd calculator
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

### Other scripts

| Command | Description |
|---|---|
| `npm run build` | Create a production build |
| `npm run preview` | Preview the production build locally |
| `npm run check` | Type-check the project with `svelte-check` |

## Project structure

```
src/
├── lib/Icons/       # SVG icon components for the operator buttons
└── routes/          # +layout.svelte and +page.svelte (the calculator)
static/              # Sound effect, favicon and images
todolist/            # A separate small SvelteKit to-do app kept in this repository
```
