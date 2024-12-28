# Meshly Frontend core

Meshly is a modern frontend for workplace communication, enabling real-time messaging, channels, and collaboration. Built for productivity with a sleek, responsive interface

# Installation

### Clone

```bash
git clone git@github.com:Mesh-ly/frontend-core.git
```

### Install Node version

```bash
nvm i 21.7.3
nvm use 21.7.3
npm i
```

### Scripts

Run the Development Server

```bash
npm run dev
```

Lint the Codebase (Recommended)

```
npm run lint
```

Build for Production

```bash
npm run build
```

Preview the Production Build

```bash
npm run preview
```

# Coding convention

## Directory Structure

src/

`├──`[`components`](./components) — Create reusable components: Button, List, etc<br>
`├──`[`pages`](./pages) — The real UI for each page makeup of many components, Login, Dashboard, etc.<br>
`├──`[`helpers`](./helpers) — Write helpers method for handling logic: parseTime, roundNumber, etc.<br>
`├──`[`routes`](./routes) — Application routes and page (screen) components<br>
`├──`[`hooks`](./hooks) — Declare all the custom hooks<br>
`├──`[`main.tsx`](./main.tsx) — Single-page application (SPA) entry point<br>
`├──`[`services`](./services) — Write all the API calls<br>
`├──`[`stores`](./stores) — Global state for the FE. Gonna use redux toolkit for this<br>
`└──`[`styles`](./styles) — Declare all the custom styling for FE<br>

# Production notes

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ["./tsconfig.node.json", "./tsconfig.app.json"],
      tsconfigRootDir: import.meta.dirname,
    },
  },
});
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from "eslint-plugin-react";

export default tseslint.config({
  // Set the react version
  settings: { react: { version: "18.3" } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs["jsx-runtime"].rules,
  },
});
```
