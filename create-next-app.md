---
name: create-next-app
description: Create a new Next.js app with TypeScript
invocation: /create-next-app
---

# Create Next.js App with TypeScript

When the user invokes this skill, create a new Next.js application.

## Steps:

1. Ask for the project name if not provided as an argument
2. Run: `npx create-next-app@latest <project-name> --typescript --tailwind --eslint --app --src-dir --import-alias "@/*"`
3. Inform the user the app is ready and how to start it (`npm run dev`)

## After setup, offer:

- Prisma for database
- NextAuth.js for authentication
- shadcn/ui for components
