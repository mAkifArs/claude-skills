---
name: create-next-app
description: Create a new Next.js app with TypeScript
---

# Create Next.js App with TypeScript

When the user invokes this skill, create a new Next.js application.

## Steps:

1. Ask for the project name if not provided as an argument
2. Run: `npx create-next-app@latest <project-name> --typescript --tailwind --eslint --app --src-dir --import-alias "@/*"`
3. Navigate into the project directory
4. Install additional dependencies (see below)

## Always include:

### React Compiler (auto-memoization)
```bash
npm install -D babel-plugin-react-compiler
```
- Add React Compiler plugin to `next.config.js` for automatic memoization
- No more manual useMemo/useCallback needed
- Next.js 15+ has experimental support built-in

### Vitest (unit testing)
```bash
npm install -D vitest @vitejs/plugin-react @testing-library/react @testing-library/jest-dom jsdom
```
- Create `vitest.config.ts` configured for Next.js
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
- Works great with Next.js App Router and Server Components

## Folder structure to create:

```
src/
├── app/                     # Next.js App Router
│   ├── layout.tsx
│   ├── page.tsx
│   ├── globals.css
│   └── (routes)/            # Route groups
├── components/              # Reusable UI components
│   └── Button/
│       ├── Button.tsx
│       ├── Button.test.tsx
│       └── index.ts
├── hooks/                   # Custom hooks
├── services/                # API calls, external services
├── utils/                   # Helper functions
├── types/                   # TypeScript types/interfaces
├── constants/               # App-wide constants
├── store/                   # Zustand stores
└── __tests__/               # Unit tests
```

Create these folders and add a sample Button component to demonstrate the pattern.

## After setup, inform user:

- `npm run dev` - Start development server
- `npm run test` - Run unit tests with Vitest
- `npm run e2e` - Run E2E tests with Cypress
- react-scan is active in dev mode to highlight re-renders

## Optional enhancements to offer:

- Prisma for database
- NextAuth.js (Auth.js) for authentication
- shadcn/ui for components
- React Query (TanStack Query) for server state
