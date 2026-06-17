# Taskly — Task Management App

A clean, responsive task management application built with vanilla HTML, CSS, and JavaScript. No build step required — just open and run.

## Features

- **Authentication** — sign up / sign in with localStorage-backed session persistence
- **CRUD tasks** — create, read, update, delete tasks with title, description, priority, status, due date, and assignee
- **Dashboard stats** — live counts for total, in-progress, completed, and high-priority tasks
- **Sidebar views** — filter by All, Today, In Progress, Completed, or Priority level
- **Status filters** — quick filter bar for To do / In progress / Done
- **Search** — real-time search across task title and description (`Ctrl+K` / `Cmd+K`)
- **Overdue detection** — tasks past their due date are highlighted in red
- **Dark mode** — follows system preference automatically
- **Responsive** — works on mobile, tablet, and desktop

## Demo account

```
Email:    alice@taskly.app
Password: password123
```

## Project structure

```
taskly/
├── index.html                  # App shell & markup
├── vercel.json                 # Vercel deployment config
├── public/
│   └── favicon.svg
└── src/
    ├── styles/
    │   └── main.css            # All styles (CSS variables, dark mode)
    └── components/
        ├── auth.js             # Auth module (login, signup, session)
        ├── tasks.js            # Tasks CRUD module
        ├── ui.js               # UI helpers (toast, show/hide, DOM)
        └── app.js              # Main controller — wires everything together
```

## Run locally

No build step needed. Just open `index.html` in a browser, or use any static server:

```bash
# Option 1 — Python
python3 -m http.server 3000

# Option 2 — Node (npx)
npx serve .

# Option 3 — VS Code
# Install the "Live Server" extension and click "Go Live"
```

## Deploy to Vercel

### One-click (recommended)

1. Push this folder to a GitHub repository
2. Go to [vercel.com](https://vercel.com) → **Add New Project**
3. Import your GitHub repo
4. Leave all settings as default — Vercel auto-detects static sites
5. Click **Deploy**

Your app will be live at `https://your-project.vercel.app` in under a minute.

### Vercel CLI

```bash
npm i -g vercel
vercel
```

## Push to GitHub

```bash
cd taskly
git init
git add .
git commit -m "Initial commit — Taskly task manager"
git remote add origin https://github.com/YOUR_USERNAME/taskly.git
git branch -M main
git push -u origin main
```

## Extending to a real backend

The `auth.js` and `tasks.js` modules are designed as drop-in replacements. To connect a real API:

- **auth.js** — replace `localStorage` reads/writes with `fetch('/api/auth/login')` etc.
- **tasks.js** — replace `localStorage` with `fetch('/api/tasks')` REST calls
- Add JWT token storage and pass `Authorization: Bearer <token>` headers

Suggested stack: **Node + Express + PostgreSQL** or **Supabase** (instant REST + auth).

## License

MIT
