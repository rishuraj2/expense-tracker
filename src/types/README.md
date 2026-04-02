# Types Directory

This directory contains shared TypeScript type definitions used across the application.

## Purpose
The `types` folder is responsible for defining reusable and generic type definitions that are shared across multiple parts of the application. It helps maintain consistency, improve type safety, and avoid duplication.

## Responsibilities
- Define shared types and interfaces used across components, services, hooks, and models
- Store utility types and type aliases
- Provide a centralized location for commonly used type definitions

## Difference Between `types` and `models`
- **models/** → Domain-specific data structures (e.g., Expense, Category)
- **types/** → Generic or shared types (e.g., IDs, API responses, enums, utility types)

## Examples

### Basic Type Alias

```ts
export type ID = string;
```

### Union Types
```ts
export type Status = "success" | "error" | "loading";
```

### API Response Type
```ts
export interface ApiResponse<T> {
  data: T;
  error?: string;
}
```

### Utility Type
```ts
export type Nullable<T> = T | null;
```

## Guidelines
- Keep types generic and reusable
- Use type for unions, primitives, and utility types
- Use interface when defining object shapes that may be extended
- Avoid duplicating types across files
- Prefer meaningful and descriptive names

## Notes
- Types improve developer experience through better autocompletion and error checking
- Centralizing types reduces inconsistencies across the codebase
- Keep this folder lightweight and focused on shared definitions only