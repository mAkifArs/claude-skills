# Code Review Skill

When the user invokes this skill, review the specified file(s) or the current changes in the project.

## Usage

- `/review` - Review staged changes or recent modifications
- `/review <file>` - Review a specific file
- `/review <folder>` - Review all files in a folder
- `/review all` - Review entire codebase (all .ts, .tsx files in src/)

## How to Review All

When user runs `/review all`:
1. Use Glob to find all `.ts` and `.tsx` files in `src/`
2. Read each file
3. Provide a summary review for each file
4. End with an overall codebase health assessment

## Review Checklist

### General Code Quality
- [ ] Clear naming (variables, functions, components)
- [ ] No code duplication (DRY principle)
- [ ] Functions are small and single-purpose
- [ ] No dead code or unused imports
- [ ] Proper error handling
- [ ] No hardcoded values that should be constants
- [ ] Security issues (XSS, injection, exposed secrets)

### TypeScript
- [ ] Proper types (avoid `any`)
- [ ] Interfaces/types for props and state
- [ ] Null/undefined handled correctly
- [ ] Type guards where needed

### File Structure
- [ ] Maximum 3 levels of nesting (e.g., `src/components/Button/`)
- [ ] One component per file - no multiple components in same file
- [ ] Each component has its own folder with index.ts barrel export
- [ ] Private/child components live in parent folder, not exported in index.ts

### React Specific
- [ ] Components are small and focused
- [ ] Props have proper TypeScript interfaces
- [ ] No unnecessary re-renders (check deps arrays)
- [ ] useEffect cleanup where needed
- [ ] No state that can be derived from other state
- [ ] Event handlers don't recreate on every render (with React Compiler this is less of an issue)
- [ ] Keys in lists are stable and unique
- [ ] No direct DOM manipulation
- [ ] Custom hooks extracted for reusable logic
- [ ] Proper loading and error states

### Zustand (if applicable)
- [ ] Store is not bloated (split if needed)
- [ ] Selectors are specific (avoid selecting entire store)
- [ ] Actions are in the store, not in components

## Output Format

Provide feedback in this structure:

### Summary
Brief overall assessment (1-2 sentences)

### Issues Found
List issues by severity:
- **Critical**: Security issues, bugs that will break functionality
- **Warning**: Performance problems, potential bugs
- **Suggestion**: Style improvements, minor optimizations

### Good Practices
Highlight 1-2 things done well (if any)

### Suggested Changes
Provide specific code fixes for critical/warning issues
