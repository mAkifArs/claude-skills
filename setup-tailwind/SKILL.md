---
name: setup-tailwind
description: Add Tailwind CSS to an existing project
---

# Add Tailwind CSS to Project

Add Tailwind CSS to the current project.

## Steps:

1. Detect the project type (React, Next.js, Vue, vanilla, etc.)
2. Install dependencies: `npm install -D tailwindcss postcss autoprefixer`
3. Initialize Tailwind: `npx tailwindcss init -p`
4. Configure `tailwind.config.js` content paths based on project type
5. Add Tailwind directives to the main CSS file:
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```
6. Verify setup by suggesting a test class to add
