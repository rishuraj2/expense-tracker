# Pages Directory

This directory contains all the page-level components of the application.

## Purpose
The `pages` folder represents the different views/screens of the application. Each page corresponds to a specific route and is responsible for composing multiple components, hooks, and services to deliver a complete user-facing feature.

## Responsibilities
- Act as entry points for routes
- Compose UI using reusable components
- Integrate hooks and services for data handling
- Manage page-level state and interactions

## Structure
Pages should be organized based on features or routes:

- **Dashboard**: Overview of expenses, KPIs, and summaries
- **AddExpense**: Form to create new expenses
- **Analytics**: Visualizations and insights of spending patterns
- **Rules**: Manage budget rules and alerts

## Example

```tsx
const Dashboard = () => {
  return (
    <div>
      <h1 className="text-2xl font-bold">Dashboard</h1>
    </div>
  );
};

export default Dashboard;
```
## Usage (Routing)

```tsx
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Dashboard from "./pages/Dashboard";
import AddExpense from "./pages/AddExpense";

<Routes>
  <Route path="/" element={<Dashboard />} />
  <Route path="/add" element={<AddExpense />} />
</Routes>
```
## Guidelines
- Keep pages focused on composition, not low-level UI details
- Avoid duplicating logic; use hooks and services instead
- Keep business logic out of pages as much as possible
- Maintain clear separation between pages and reusable components
- Use consistent naming aligned with routes

## Notes
- Pages are tied to routing and should reflect user navigation flow
- They should remain relatively thin and delegate work to other layers
- Changes in pages should not affect core business logic directly