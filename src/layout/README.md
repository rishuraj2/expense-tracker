# Layout Directory

This directory contains layout components that define the overall structure and visual organization of the application.

## Purpose
The `layout` folder is responsible for composing the high-level structure of the UI, such as navigation panels, page containers, and common wrappers. Layouts ensure consistency across different pages and help separate structural concerns from feature-specific components.

## Responsibilities
- Define page structure (e.g., sidebar + main content)
- Provide shared UI elements like navigation bars or headers
- Wrap page components to maintain consistent styling and spacing
- Manage layout-level responsiveness

## Structure
Typical layout components include:

- **MainLayout**: Root layout that includes sidebar and main content area
- **AuthLayout** (optional): Layout for authentication pages
- **DashboardLayout** (optional): Layout specific to dashboard views

## Example

```tsx
import Sidebar from "../components/Sidebar";
import { Outlet } from "react-router-dom";

const MainLayout = () => {
  return (
    <div className="flex">
      <Sidebar />
      <main className="flex-1 min-h-screen p-6 bg-gray-100">
        <Outlet />
      </main>
    </div>
  );
};

export default MainLayout;
```

## Usage
```tsx
import { BrowserRouter, Routes, Route } from "react-router-dom";
import MainLayout from "./layout/MainLayout";
import Dashboard from "./pages/Dashboard";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<MainLayout />}>
          <Route index element={<Dashboard />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

## Guidelines
- Keep layout components focused on structure, not business logic
- Avoid embedding feature-specific logic inside layouts
- Use composition (children or Outlet) to render dynamic content
- Ensure layouts are reusable across multiple pages
- Maintain consistency in spacing, alignment, and responsiveness

## Notes
- Layout components act as a bridge between routing and UI structure
- They should remain stable and change less frequently than feature components
- Use Tailwind CSS for styling and responsiveness