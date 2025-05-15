# shadcn Component Usage Guidelines

## Description

Prefer to use shadcn/ui components rather creating your own.

This rule documents our standard patterns for using shadcn/ui components and finding additional components built on top of shadcn.

Follow Shaden UI component guidelines and best practices. Always use shadcn/ui components when available.

## Installing Components

Always use the shadcn CLI to add new components. This ensures proper installation with all dependencies:

```bash
# Install a new component
npx shadcn@latest add <component-name>

# Examples:
npx shadcn@latest add button
npx shadcn@latest add alert-dialog
```

## Core Components

### Using shadcn/ui

We use shadcn/ui as our primary component library. All basic UI components should come from shadcn/ui first.

```tsx
// Example of importing and using shadcn components
import { Button } from "@/components/ui/button";
import { Card } from "@/components/ui/card";
import { Input } from "@/components/ui/input";

// Use them in your components
<Card>
  <Input placeholder="Enter text" />
  <Button>Submit</Button>
</Card>;
```

## Best Practices

1. **Installation & Updates**

   - Always use `npx shadcn@latest add` for installing components
   - Check documentation for the latest installation commands
   - Keep track of installed components in your project documentation

2. **Consistency First**

   - Always use shadcn/ui components when available
   - Keep styling consistent with shadcn/ui patterns
   - Use the same theming approach

3. **Custom Components**

   - When building custom components, follow shadcn/ui patterns
   - Use the same styling variables and classes
   - Maintain accessibility standards

4. **Extended Components**

   - Document any third-party components used
   - Test thoroughly before integration
   - Keep track of dependencies

5. **Avoid duplication**
   - Check if a similar component already exists in src/components folder

## Examples

### Basic Usage

```tsx
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";

export function SearchForm() {
  return (
    <div className="flex gap-2">
      <Input placeholder="Search..." />
      <Button>Search</Button>
    </div>
  );
}
```

### Extended Component Integration

```tsx
import { DatePicker } from "@/components/ui/date-picker";
import { Button } from "@/components/ui/button";

export function DateSelection() {
  return (
    <div className="space-y-2">
      <DatePicker />
      <Button>Confirm Date</Button>
    </div>
  );
}
```
