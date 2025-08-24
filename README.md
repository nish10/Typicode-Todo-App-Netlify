# Typicode Todo App (Netlify)

Live demo ➜ **https://sweet-tanuki-67c12c.netlify.app/**

A tiny, no-build front‑end app that uses the free **JSONPlaceholder** mock API to seed a few todos, lets you **add** new ones, **toggle complete** with a single click, and **delete** a todo with a double‑click.

> ⚠️ JSONPlaceholder is a mock service. Writes appear to succeed in responses but **are not persisted** on the server. This app updates the UI optimistically.

---

## Features

- Fetch starter todos from JSONPlaceholder
- Add a new todo
- **Single‑click** an item to toggle _completed ✓ / not completed ○_
- **Double‑click** an item to delete it
- Minimal, vanilla HTML/CSS/JS (no frameworks)
- Works as a static site (perfect for Netlify/GitHub Pages)

---

## How it works

- Initial load: fetches todos from `https://jsonplaceholder.typicode.com/todos` (often with a `?_limit=N` query to keep it short)
- Add: `POST /todos` with `{ title, completed: false }`
- Toggle: `PUT /todos/:id` (or `PATCH`) with `{ completed }`
- Delete: `DELETE /todos/:id`

Since the API is mock-only, the UI reflects changes immediately. A page refresh will fetch the original mock list again.

---

## Usage (UI)

- **Add**: type a title in the input and submit.
- **Toggle complete**: _single‑click_ any todo row.
- **Delete**: _double‑click_ the same row.
- Completed items may show a line‑through / “done” style.

---

## Local development

1. Clone or download the project files.
2. Open `index.html` directly, **or** serve locally:
   ```bash
   # any static server works; here are a few options
   python -m http.server 5173
   # or
   npx serve .
   ```
3. Visit `http://localhost:5173` (or whatever your server prints).

> If your code limits the initial fetch (e.g. `?_limit=5`), adjust the number as you like.

---

## Deploying to Netlify

1. Create a new **Netlify** site from your repo/folder (no build step needed).
2. Set **Publish directory** to the project root (contains `index.html`).
3. Deploy. Your app will be served as a static site (like the demo link above).

---

## Notes & limitations

- JSONPlaceholder responses are **fake writes**. Treat this project as a UI demo.
- Network failures are handled minimally; feel free to add retries/toasts.
- Double‑click delete is intentional; change to a button if you prefer.

---

## Credits

- API: [JSONPlaceholder](https://jsonplaceholder.typicode.com/)
- Hosting: Netlify
