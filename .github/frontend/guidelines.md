# Frontend Development Guidelines

You are a senior frontend developer and an expert in TypeScript, React, Tailwind CSS, shadcn/ui, and axios.

Check if component already exists. If not, prioritize using shadcn/ui components rather creating your own. Refer to [Shadcn guidelines](./react/shadcn-guidelines.md) for more instructions.

Always follow [TypeScript guidelines](./react/typescript-guidelines.md). For custom components use [React guildelines](./react/react-guidelines.md)

## General Guidelines

- Write clean, maintainable, and well-documented code
- Follow established patterns in the codebase
- Prioritize component reusability and testability
- Implement proper error handling and loading states
- Use TypeScript's type system to its full potential
- Keep dependencies minimal and up-to-date
- For specific implementation details, refer to the `/src/react` folder

## Folder Structure

- **Source Directory (`src/`)**:

  - `components/`: Reusable UI components
    - Organize by feature (e.g., `auth/`, `dashboard/`)
    - Group related components in subdirectories
  - `hooks/`: Custom React hooks
  - `services/`: API and data fetching logic
  - `utils/`: Helper functions and utilities
  - `types/`: TypeScript interfaces and type definitions
  - `context/`: React context providers
  - `pages/`: (If not using Next.js) Component-based routes
  - `assets/`: Static files (images, icons)
  - `styles/`: Global styles and Tailwind configuration

- **Component Organization**:
  - For complex components: use a directory with index.ts exporting the component
  - Keep related files together (component, hooks, utils)
  - Use kebab-case for component files (e.g., `my-button.tsx`)

## Code Style and Structure

- Use functional and declarative programming patterns; avoid classes
- Prefer pure functions when possible
- Keep components small and focused on a single responsibility
- Extract complex logic into custom hooks
- Use appropriate React patterns (composition over inheritance)

## Naming Conventions

- Use lowercase with dashes for directories (e.g., `components/auth-wizard`)
- Favor named exports for components
- Use PascalCase for component names (e.g., `AuthButton`)
- Use camelCase for variables, functions, and instances
- Prefix boolean variables with "is", "has", or "should" (e.g., `isLoading`)

## TypeScript Usage

- Use TypeScript for all code
- Define explicit return types for functions
- Use interfaces for objects with methods, types for simpler structures
- Avoid using `any` type; use `unknown` when type is uncertain
- Leverage generics for reusable components and functions
- Create shared type definitions in the `types/` directory

## UI and Styling

- Use shadcn/ui and Tailwind CSS for components and styling
- Implement responsive design with Tailwind CSS; use a mobile-first approach
- Follow consistent spacing and sizing using Tailwind's scale
- Extract common utility patterns into reusable components
- Use CSS variables for theming through Tailwind configuration
