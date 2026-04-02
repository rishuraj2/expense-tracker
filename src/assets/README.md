# Assets Directory

This directory contains all static resources used across the application.

## Purpose

The assets folder is responsible for storing files that are not part of the application logic but are required for UI rendering and user experience.

## Contents

Typical files stored here include:
- Images (icons, illustrations, logos)
- Fonts
- Static JSON/mock data (if any)
- SVGs and media files

## Guidelines
- Keep assets organized in subfolders (e.g., images/, icons/, fonts/)
- Use meaningful and consistent naming conventions
- Optimize images to reduce bundle size
- Avoid storing large or unnecessary files

## Usage

Assets can be imported directly into components:
```ts
import logo from "../assets/images/logo.png";
```
Or referenced in CSS when needed.

## Notes
- Do not include business logic in this directory
- This folder should only contain static, reusable resources