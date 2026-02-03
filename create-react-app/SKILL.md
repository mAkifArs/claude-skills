---
name: create-react-app
description: Create a new React app with TypeScript
---

# Create React App with TypeScript

When the user invokes this skill, create a new React application with TypeScript using Vite.

## Steps to follow:

1. Ask the user for the project name if not provided as an argument
2. Run: `npm create vite@latest <project-name> -- --template react-ts`
3. Navigate into the project directory
4. Install dependencies with `npm install`

## Always include:

### React Compiler (auto-memoization)
```bash
npm install -D babel-plugin-react-compiler
```
- Add React Compiler plugin to Vite config for automatic memoization
- No more manual useMemo/useCallback needed

### Vitest (unit testing)
```bash
npm install -D vitest @testing-library/react @testing-library/jest-dom jsdom
```
- Configure vitest in `vite.config.ts`
- Create sample test file in `src/__tests__/`
- Add `test` script to package.json

### Cypress (E2E testing)
```bash
npm install -D cypress
```
- Initialize with `npx cypress open`
- Add `cypress` folder structure
- Add `e2e` and `e2e:headless` scripts to package.json

### react-scan (detect re-renders)
```bash
npm install -D react-scan
```
- Add react-scan to development setup for visualizing unnecessary re-renders
- Configure to run only in development mode

### Zustand (global state management)
```bash
npm install zustand
```
- Create `src/store/` folder for store files
- Create a sample store with TypeScript types
- Lightweight, no boilerplate, no providers needed

## Folder structure to create:

```
src/
├── components/          # Reusable UI components
│   └── Button/
│       ├── Button.tsx
│       ├── Button.test.tsx
│       └── index.ts
├── pages/               # Route-level components
├── hooks/               # Custom hooks
├── services/            # API calls, external services
├── utils/               # Helper functions
├── types/               # TypeScript types/interfaces
├── constants/           # App-wide constants
├── store/               # Zustand stores
├── assets/              # Images, fonts, etc.
└── __tests__/           # Unit tests
```

Create these folders and add a sample Button component to demonstrate the pattern.

## After setup, inform user:

- `npm run dev` - Start development server
- `npm run test` - Run unit tests with Vitest
- `npm run e2e` - Run E2E tests with Cypress
- react-scan is active in dev mode to highlight re-renders

## Optional enhancements to offer:

- ESLint + Prettier setup
- Tailwind CSS
- React Router
