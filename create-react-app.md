---
name: create-react-app
description: Create a new React app with TypeScript
invocation: /create-react-app
---

# Create React App with TypeScript

When the user invokes this skill, create a new React application with TypeScript using Vite (the modern recommended approach).

## Steps to follow:

1. Ask the user for the project name if not provided as an argument
2. Run: `npm create vite@latest <project-name> -- --template react-ts`
3. Navigate into the project directory
4. Install dependencies with `npm install`
5. Inform the user the app is ready and how to start it (`npm run dev`)

## Optional enhancements to offer:

- ESLint + Prettier setup
- Tailwind CSS
- React Router
- Testing setup (Vitest + React Testing Library)

Ask the user if they want any of these additions after the base setup is complete.
