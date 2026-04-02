# Models Directory

This directory contains the core data models and type definitions used throughout the application.

## Purpose
The `models` folder defines the structure of the data used in the application. It acts as a central source of truth for entities such as expenses, categories, and rules. These models ensure type safety, consistency, and clarity across different layers of the application.

## Responsibilities
- Define data structures using TypeScript interfaces, types, or classes
- Represent core entities of the application (e.g., Expense, Category, Rule)
- Provide a consistent contract between components, services, and hooks
- Enable strong typing and reduce runtime errors

## Structure
Models should be organized based on domain entities:

- **Expense**: Represents an individual expense entry
- **Category**: Defines categories for expenses
- **Rule**: Represents alerting or budget rules

## Example

```ts
export interface Expense {
  id: string;
  amount: number;
  category: string;
  date: string;
  note?: string;
}
```

## Advanced Usage (Optional)
Using classes for behavior:
```tsx
export class ExpenseModel {
  constructor(
    public id: string,
    public amount: number,
    public category: string,
    public date: string
  ) {}

  isHighValue(threshold: number): boolean {
    return this.amount > threshold;
  }
}
```
## Guidelines
- Use clear and descriptive names for models
- Prefer interfaces/types for simple data structures
- Use classes only when behavior (methods) is required
- Keep models independent of UI and framework-specific logic
- Avoid embedding business logic inside models unless necessary

## Notes
- Models act as a contract between different layers (components, services, hooks)
- Changes to models should be carefully managed as they impact multiple parts of the application
- Keep models simple, predictable, and reusable
