# TypeScript Guidelines for React Development

- **Follow TypeScript best practices** for type safety and code maintainability.
- **Naming Conventions**: Follow clear and consistent naming conventions.

## Best Practices

1. **Prop Types**: Define types for component props with descriptive names. Prefer types over interfaces for consistency.

   ```tsx
   type UserProfileProps = {
     user: User;
     isEditable?: boolean;
     onUpdate: (updatedUser: User) => void;
   };
   ```

2. **Event Typing**: Use proper TypeScript event types from React.

   ```tsx
   const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
     // Type-safe event handling
   };
   ```

3. **Generic Components**: Leverage TypeScript generics for reusable components.

   ```tsx
   type ListProps<T> = {
     items: T[];
     renderItem: (item: T) => React.ReactNode;
   };

   function List<T>({ items, renderItem }: ListProps<T>) {
     return <>{items.map(renderItem)}</>;
   }
   ```

4. **Type Assertions**: Minimize use of `as` type assertions; prefer type guards.

5. **State Typing**: Always type your state properly.

   ```tsx
   type UserState = {
     data: User | null;
     isLoading: boolean;
     error?: string;
   };

   const [userState, setUserState] = useState<UserState>({
     data: null,
     isLoading: true,
   });
   ```

6. **Enum vs Union Types**: Prefer union types for simple cases.

   ```tsx
   // Instead of enum
   type Status = "idle" | "loading" | "success" | "error";
   ```

7. **Function Components**: Use explicit return type for complex components.

   ```tsx
   const ProfileCard = ({ user }: ProfileCardProps): JSX.Element => {
     // Component logic
   };

   // Or
   function ProfileCard(props: ProfileCardProps): JSX.Element {
     // Component logic
   }
   ```

8. **Custom Hooks**: Type the return values of custom hooks.

   ```tsx
   function useUser(id: string): { user: User | null; isLoading: boolean } {
     // Hook implementation
   }
   ```

9. **Avoid `any` Type**: Avoid `any` type as it bypasses TypeScript's type checking. Use `unknown` for truly unknown values, and then narrow the type with type guards.

   ```tsx
   // Avoid
   function processData(data: any): void {
     /* ... */
   }

   // Prefer
   function processData(data: unknown): void {
     if (typeof data === "string") {
       // Now TypeScript knows data is a string
     } else if (Array.isArray(data)) {
       // Now TypeScript knows data is an array
     }
   }
   ```

10. **Import React Elements**: Import specific elements from React rather than using React namespace.

    ```tsx
    // Avoid
    const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
      // Type-safe event handling
    };

    // Prefer
    import { ChangeEvent } from "react";

    const handleChange = (e: ChangeEvent<HTMLInputElement>) => {
      // Type-safe event handling
    };
    ```

11. **Fragment Shorthand**: Always se the shorthand syntax for React Fragments.

    ```tsx
    // Avoid
    return (
      <React.Fragment>
        <Child1 />
        <Child2 />
      </React.Fragment>
    );

    // Prefer
    return (
      <>
        <Child1 />
        <Child2 />
      </>
    );
    ```

12. **Avoid Namespace Imports**: Don't use namespace imports with React.

    ```tsx
    // Avoid
    import * as React from "react";

    // Prefer
    import { useState, useEffect, FC } from "react";
    ```
