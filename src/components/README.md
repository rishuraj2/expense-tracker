# Components Directory

This directory contains all reusable UI components used throughout the application.

## Purpose
The `components` folder is responsible for building the visual structure of the application. It includes modular, reusable pieces of UI that can be composed to create pages and layouts.

## Structure
Components should be organized based on their responsibility and reusability:

- **Common components**: Generic UI elements (e.g., Button, Input, Modal)
- **Feature-specific components**: Components tied to a specific feature (e.g., ExpenseCard, CategorySelector)
- **Layout components**: Structural elements (e.g., Sidebar, Navbar)

## Guidelines
- Keep components small and focused (Single Responsibility Principle)
- Prefer composition over large monolithic components
- Use TypeScript for strict typing of props
- Avoid embedding business logic directly in components; delegate it to services or hooks
- Maintain consistent naming conventions (PascalCase for component names)

## Example

```tsx
type ButtonProps = {
  label: string;
  onClick: () => void;
};

const Button = ({ label, onClick }: ButtonProps) => {
  return (
    <button onClick={onClick} className="px-4 py-2 bg-blue-500 text-white rounded">
      {label}
    </button>
  );
};

export default Button;
```

## Usage
```ts
import Button from "../components/Button";

<Button label="Add Expense" onClick={handleClick} />
```

## Note
- Components should be reusable and not tightly coupled to a specific page
- Styling should be handled using Tailwind CSS
- Keep UI logic separate from data and state management layers