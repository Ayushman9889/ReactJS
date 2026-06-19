# ⚛️ ReactJS Learning Repository

A structured, project-by-project React.js learning repository — starting from raw `react-dom` rendering, moving through Vite setup, hooks, Tailwind CSS, custom hooks, React Router, and the Context API, finishing with two complete Context-API-powered apps.

This repository serves as:

- 📚 **Personal revision notes** — each project isolates one concept
- 💡 **React practice collection** — 11 small, runnable projects
- 🎯 **Interview preparation resource** — hooks, custom hooks, Context API, React Router, controlled inputs
- 🤝 **Learning reference for beginners** — numbered folders form a step-by-step path

---

## 📁 Repository Structure

```
ReactJS/
│
├── 01basicreact/              ← Plain Create-React-App setup (no Vite)
│   └── src/
│       ├── App.js              ← Root component rendering <Chai />
│       └── Chai.jsx             ← Simplest possible functional component
│
├── 01vitereact/                ← Same concept, scaffolded with Vite instead of CRA
│   └── src/
│       ├── App.jsx              ← Renders <Chai />, a variable, and JSX text
│       └── chai.jsx             ← Minimal component
│
├── 02counter/                  ← First interactive component
│   └── src/App.jsx              ← useState, batched state updates, click handlers
│
├── 03tailwindprops/             ← Styling + component reuse
│   └── src/
│       ├── App.jsx              ← Renders <Card /> twice with different props
│       └── components/Card.jsx  ← Props, default prop values, destructuring
│
├── 04bgChanger/                ← Dynamic inline styles
│   └── src/App.jsx              ← useState driving a live background color
│
├── 05passwordGenerator/         ← Multiple hooks working together
│   └── src/App.jsx              ← useState, useCallback, useEffect, useRef
│
├── 06currencyConvertor/         ← Custom hooks + component composition
│   └── src/
│       ├── App.jsx              ← Form, swap logic, controlled conversion
│       ├── components/
│       │   ├── InputBox.jsx     ← Reusable input + currency selector
│       │   └── index.js         ← Barrel export
│       └── hooks/
│           └── useCurrencyInfo.js ← Custom hook wrapping a live exchange-rate API
│
├── 07reactRouter/               ← Client-side routing
│   └── src/
│       ├── main.jsx             ← createBrowserRouter + createRoutesFromElements
│       ├── Layout.jsx           ← Shared layout using <Outlet />
│       └── components/
│           ├── Header/          ← <NavLink> active-route styling
│           ├── Footer/
│           ├── Home/
│           ├── About/
│           ├── Contact/
│           ├── User/            ← Dynamic route param via useParams()
│           └── Github/          ← Route data loading via a router loader
│
├── 08miniContext/               ← First Context API example
│   └── src/
│       ├── context/
│       │   ├── UserContext.js          ← React.createContext()
│       │   └── UserContextProvider.jsx ← Provider wrapping state
│       └── components/
│           ├── Login.jsx        ← Writes to context
│           └── Profile.jsx      ← Reads from context
│
├── 09themeswitcher/             ← Context API for global UI state (dark/light mode)
│   └── src/
│       ├── contexts/theme.js    ← createContext + custom useTheme() hook
│       └── components/
│           ├── ThemeBtn.jsx     ← Toggle switch consuming the theme context
│           └── Card.jsx         ← UI that responds to the `dark:` Tailwind classes
│
├── 10todocontextLocal/          ← Capstone: Context API + localStorage
│   └── src/
│       ├── contexts/TodoContext.js     ← createContext + useTodo() hook
│       └── components/
│           ├── TodoForm.jsx     ← Add todos
│           ├── TodoItem.jsx     ← Edit, complete, delete a single todo
│           └── index.js         ← Barrel export
│
├── contextNotes.md              ← Reference snippets used while building Context API projects
├── currency.md                  ← Reference snippets used while building the currency converter
├── reactRouterNotes.md          ← Reference snippets used while building React Router project
└── todoContextapiNotes.md       ← Reference snippets used while building the Todo app
```

---

## 📚 Topics Covered, Project by Project

| # | Project | Core Concept | Key APIs / Patterns |
|---|---------|--------------|----------------------|
| 1 | `01basicreact` | React without a build tool wrapper feel (CRA) | `function Component()`, `export default`, JSX fragments |
| 1 | `01vitereact` | Vite as the build tool instead of CRA | Same JSX basics, faster dev server |
| 2 | `02counter` | State and re-renders | `useState`, functional updates (`prevState => ...`), batched `setState` calls |
| 3 | `03tailwindprops` | Component reusability | Props, prop destructuring, default parameter values, Tailwind utility classes |
| 4 | `04bgChanger` | Derived UI from state | Inline `style={{}}` driven by `useState`, conditional styling via click handlers |
| 5 | `05passwordGenerator` | Hook composition | `useState`, `useCallback` (memoized functions), `useEffect` (auto-regenerate), `useRef` (DOM access, clipboard copy) |
| 6 | `06currencyConvertor` | Custom hooks & data fetching | Custom hook (`useCurrencyInfo`), `fetch` inside `useEffect`, controlled form, swap logic |
| 7 | `07reactRouter` | Client-side routing (React Router v6) | `createBrowserRouter`, `createRoutesFromElements`, `<Outlet />`, `<Link>` / `<NavLink>`, `useParams`, route `loader` + `useLoaderData` |
| 8 | `08miniContext` | Context API fundamentals | `createContext`, `Context.Provider`, `useContext`, lifting state into a provider |
| 9 | `09themeswitcher` | Global UI state with Context | Custom `useTheme()` hook wrapping `useContext`, syncing context state to the DOM (`classList`) via `useEffect` |
| 10 | `10todocontextLocal` | Full CRUD app with Context + persistence | Context-based CRUD (`addTodo`, `updateTodo`, `deleteTodo`, `toggleComplete`), `localStorage` sync via two `useEffect` hooks, controlled editable list items |

---

## 🧠 Concepts Covered Across the Repository

- **Core React**: JSX, functional components, fragments, props, conditional rendering, list rendering with `key`
- **Hooks**: `useState`, `useEffect`, `useCallback`, `useRef`, `useId`, `useContext`, custom hooks
- **State management**: local component state, lifting state up, global state via the Context API
- **Forms**: controlled inputs, `onSubmit` with `preventDefault`, checkboxes, range sliders, `<select>` dropdowns
- **Routing**: nested routes, layouts with `<Outlet />`, dynamic segments (`/user/:userid`), data loaders
- **Styling**: Tailwind CSS utility classes, dynamic/conditional class names, dark-mode toggling
- **Persistence & APIs**: `localStorage` read/write, `fetch` against public APIs (GitHub API, currency exchange-rate API)
- **Tooling**: both Create React App (`01basicreact`) and Vite (every other project) are represented

---

## 🚀 How to Use

**Clone the repository:**
```bash
git clone https://github.com/Ayushman9889/ReactJS.git
cd ReactJS
```

**Run any individual project:**
```bash
cd 02counter
npm install
npm run dev          # Vite projects
```

For `01basicreact` (Create React App), use:
```bash
cd 01basicreact
npm install
npm start
```

**Recommended learning path:**
```
01basicreact / 01vitereact  →  JSX & component basics
02counter                   →  useState
03tailwindprops              →  Props & Tailwind styling
04bgChanger                  →  Dynamic styling from state
05passwordGenerator          →  useEffect, useCallback, useRef
06currencyConvertor          →  Custom hooks & data fetching
07reactRouter                →  Client-side routing
08miniContext                →  Context API basics
09themeswitcher              →  Context API for global UI state
10todocontextLocal           →  Context API + localStorage (capstone project)
```

**Reference notes:**
The root-level `.md` files (`contextNotes.md`, `currency.md`, `reactRouterNotes.md`, `todoContextapiNotes.md`) contain earlier/starter snippets captured while building the corresponding numbered projects — useful for seeing the "before" state of a component.

---

## ⚙️ Prerequisites

- Node.js (v16+) and npm
- A modern browser (Chrome / Firefox / Edge)
- Internet connection for projects that call external APIs (`06currencyConvertor`, `07reactRouter`'s Github route)

---

## 🎯 Goal

This repository documents a complete React.js learning journey — from a single `<h2>` component all the way to routed, Context-API-driven applications with persisted state — while creating a resource that helps other students learn and revise React effectively.
