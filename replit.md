# Overview

This is a modern full-stack web application built with React and Express, featuring a creative portfolio website with 3D animations and interactive components. The application showcases a developer portfolio with sections for hero, about, skills, projects, and contact, enhanced with smooth animations using Framer Motion and Three.js-inspired visual effects. The backend is set up with Express.js and includes database integration using Drizzle ORM with PostgreSQL, though the current implementation uses in-memory storage for user management.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The frontend is built using **React 18** with **TypeScript** and follows a component-based architecture using functional components with hooks. The application uses **Vite** as the build tool for fast development and optimized production builds. The UI is built with **shadcn/ui** components, providing a consistent design system with **Radix UI** primitives for accessibility.

**Styling** is handled through **Tailwind CSS** with a custom design system that includes CSS variables for theming. The application features custom color schemes with gradients and supports responsive design patterns.

**State Management** uses **TanStack Query** (React Query) for server state management and **React Hook Form** with **Zod** validation for form handling. Local component state is managed through React's built-in useState and useContext hooks.

**Routing** is implemented using **Wouter**, a lightweight client-side routing solution that provides navigation between different sections of the portfolio.

**Animations** are powered by **Framer Motion** for smooth page transitions and component animations, with custom 3D visual effects simulated through CSS animations rather than full Three.js implementation.

## Backend Architecture
The backend follows a **REST API** pattern built with **Express.js** and **TypeScript**. The server architecture includes:

- **Express middleware** for JSON parsing, URL encoding, and request logging
- **Route registration system** with centralized route management
- **Error handling middleware** for consistent error responses
- **Development vs Production** environment handling with Vite integration for development

**Storage Interface** implements an abstraction layer with `IStorage` interface that currently uses in-memory storage (`MemStorage`) but is designed to be easily swapped with database implementations. The storage handles user management with CRUD operations.

## Database Design
The application is configured for **PostgreSQL** using **Drizzle ORM** for type-safe database operations. The schema defines a users table with:
- UUID primary keys with automatic generation
- Username and password fields with appropriate constraints
- Zod schema validation for insert operations

**Database Configuration** uses Drizzle Kit for migrations and schema management, with connection via environment variables.

## Development Environment
The project uses a **monorepo structure** with separate client and server directories, plus shared types and schemas. **TypeScript** is configured with strict mode and path aliases for clean imports.

**Build Process** includes:
- Vite for frontend bundling with React plugin
- ESBuild for backend bundling
- Development server with hot module replacement
- Production builds with optimized static assets

# External Dependencies

## UI and Styling
- **Radix UI** components for accessible UI primitives (dialogs, dropdowns, forms, etc.)
- **Tailwind CSS** for utility-first styling with PostCSS processing
- **class-variance-authority** and **clsx** for dynamic class name generation
- **Framer Motion** for animations and transitions
- **Embla Carousel** for carousel components

## Backend Services
- **Neon Database** (`@neondatabase/serverless`) for PostgreSQL hosting
- **Express.js** for the web server framework
- **Drizzle ORM** with **drizzle-zod** for database operations and validation

## Development Tools
- **Vite** with React plugin and runtime error overlay for development
- **TypeScript** for type safety across the entire stack
- **ESLint** and development utilities for code quality
- **Replit-specific plugins** for development environment integration

## Form and Data Management
- **React Hook Form** with **Hookform Resolvers** for form handling
- **TanStack React Query** for server state management and caching
- **Zod** for runtime type validation and schema definition
- **date-fns** for date manipulation utilities

## Assets and Media
- Google Fonts integration for typography (Poppins, Inter, Architects Daughter, etc.)
- Custom asset handling through Vite aliases
- Image assets stored in attached_assets directory