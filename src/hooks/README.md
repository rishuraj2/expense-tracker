# Hooks Directory

This directory contains all custom React hooks used across the application.

## Purpose
The `hooks` folder is responsible for encapsulating reusable logic that can be shared across multiple components. It helps in separating business logic from UI, making components cleaner and more maintainable.

## What are Hooks?
Hooks are functions that allow you to use React features such as state, lifecycle, and context in functional components.

Custom hooks follow the naming convention:
useSomething()

## Structure
Hooks can be categorized based on their responsibility:

- **State hooks**: Manage reusable state logic (e.g., `useExpenses`)
- **Utility hooks**: Encapsulate reusable behaviors (e.g., `useDebounce`, `useLocalStorage`)
- **Feature-specific hooks**: Logic tied to a specific feature (e.g., `useExpenseAnalytics`)
- **Integration hooks**: Handle API calls or external services

## Guidelines
- Always prefix hooks with `use`
- Keep hooks focused on a single responsibility
- Do not include UI rendering logic inside hooks
- Use hooks to abstract complex logic away from components
- Ensure hooks are reusable and composable
- Avoid unnecessary state duplication

## Example

```tsx
import { useState } from "react";

export const useCounter = () => {
  const [count, setCount] = useState(0);

  const increment = () => setCount((prev) => prev + 1);
  const decrement = () => setCount((prev) => prev - 1);

  return { count, increment, decrement };
};
```
## Usage
```tsx
import { useCounter } from "../hooks/useCounter";

const Counter = () => {
  const { count, increment, decrement } = useCounter();

  return (
    <div>
      <p>{count}</p>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
    </div>
  );
};
```
## Note
- Hooks should not directly manipulate DOM elements
- Keep side effects controlled using useEffect
- Prefer hooks over duplicating logic in multiple components
- Combine hooks to build more complex behavior when needed