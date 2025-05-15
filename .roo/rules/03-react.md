# React Development Guidelines

**Use Shadcn/ui**: Prioritize using shadcn/ui components rather creating your own. Refer to [Shadcn guidelines](./04-shadcn.md) for more instructions

## Component Structure

1. **Functional Components**: Prefer functional components with hooks over class components.
2. **Single Responsibility**: Each component should do one thing well.
3. **Size Limit**: Keep components under 300 lines if possible; split larger components.
4. **Folder Structure**: Organize by feature, not by type.

## State Management

1. **Local State**: Use `useState` for simple component-level state.
2. **Complex State**: Use `useReducer` for complex state logic.
3. **Context API**: Use for state that many components need.
4. **External Libraries**: Zustand only for complex applications.

## Performance Optimization

1. **Memoization**: Use `React.memo`, `useMemo`, and `useCallback` judiciously.
2. **Avoid Renders**: Prevent unnecessary renders by structuring state properly.

## Best Practices

1. **Keys**: Always use stable, unique keys for list items.
2. **Prop Drilling**: Limit to 2-3 levels; use Context for deeper hierarchies.
3. **Event Handlers**: Use consistent naming (`handleEventName`).
4. **TypeScript**: Follow [TypeScript guidelines](./05-typescript.md) for proper typing.

## Hooks Guidelines

1. **Rules of Hooks**: Follow React's rules of hooks strictly.
2. **Custom Hooks**: Extract reusable logic into custom hooks.
3. **Dependencies**: Keep dependency arrays accurate and complete.
4. **Effect Cleanup**: Always return cleanup functions from useEffect when necessary.

## Styling Approaches

1. **Tailwind CSS**: Use Tailwind CSS as the primary styling solution for its utility-first approach and rapid development.

   - Follow the official [Tailwind CSS style guide](https://tailwindcss.com/docs)
   - Use custom theme configuration for project-specific design tokens
   - Create component abstractions for repeated UI patterns
   - Leverage JIT mode for optimal performance

2. **CSS Modules**: Use for rare cases where Tailwind doesn't provide needed functionality.

3. **Global Styles**: Minimize; use only for base HTML element styling and design tokens.

4. **Inline Styles**: Avoid except for dynamically calculated values that can't be handled by Tailwind.

## Testing

1. **Unit Tests**: Test component rendering and interactions.
2. **Integration Tests**: Test component interactions within features.
3. **Testing Library**: Use React Testing Library with Jest.
4. **Mocking**: Mock external dependencies and complex hooks.
