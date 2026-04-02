# Services Directory

This directory contains all business logic and data-handling services used across the application.

## Purpose
The `services` folder is responsible for implementing the core logic of the application. It acts as an abstraction layer between the UI (components/pages) and the data layer (APIs, storage, or mock data).

## Responsibilities
- Handle business logic (e.g., expense calculations, validations)
- Interact with data sources (APIs, local storage, etc.)
- Provide reusable methods for data operations
- Abstract implementation details from UI components

## Structure
Services should be organized based on domain features:

- **ExpenseService**: Handles operations related to expenses (add, delete, update, fetch)
- **RuleService**: Manages budget rules and alert logic
- **AnalyticsService**: Computes insights and trends from data

## Example

```ts
import { Expense } from "../models/Expense";

export class ExpenseService {
  private expenses: Expense[] = [];

  addExpense(expense: Expense) {
    this.expenses.push(expense);
  }

  getExpenses(): Expense[] {
    return this.expenses;
  }

  getTotal(): number {
    return this.expenses.reduce((sum, exp) => sum + exp.amount, 0);
  }
}
```
## Guidelines
- Keep services independent of UI frameworks (no React code inside services)
- Follow single responsibility principle
- Use interfaces to abstract implementations when needed
- Keep services reusable and testable
- Avoid directly manipulating UI state inside services

## Notes
- Services act as the core logic layer of the application
- They should be easily replaceable (e.g., switching from local storage to API)
- Properly structured services improve scalability and maintainability