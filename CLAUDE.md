# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install       # Install dependencies
npm run dev       # Start dev server at http://localhost:5173
npm run build     # Production build
npm run lint      # Run ESLint
npm run preview   # Preview production build
```

There is no test suite configured in this project.

## Architecture

This is a frontend-only React 19 SPA built with Vite. There is no backend or data persistence — all state lives in memory and resets on page refresh.

The entire application logic lives in `src/App.jsx`. State is managed with `useState` hooks:
- `transactions` — array of `{ id, description, amount, type, category, date }` objects
- Form field state for adding new transactions (`description`, `amount`, `type`, `category`)
- Filter state (`filterType`, `filterCategory`) which drives both the displayed list and the summary calculations

The summary totals (income, expenses, balance) are derived from the filtered transactions, not the full list.

Styling is plain CSS in `src/App.css` (component styles) and `src/index.css` (global reset). No CSS framework is used.

## Project Context

This is a starter project for a Claude Code course (Code with Mosh). The code is intentionally imperfect — it contains bugs, poor UI, and messy structure that are meant to be fixed as part of the course exercises.
