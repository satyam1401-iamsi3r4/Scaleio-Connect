# Overview

This is a full-stack web application built with React frontend and Express.js backend, featuring a modern tech stack with TypeScript, Tailwind CSS, and shadcn/ui components. The project includes database integration with Drizzle ORM and PostgreSQL, along with comprehensive UI components for building interactive web applications.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

The frontend is built using React with TypeScript and follows a component-based architecture:

- **Framework**: React 18 with TypeScript for type safety
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Routing**: wouter for lightweight client-side routing
- **State Management**: TanStack React Query for server state management
- **Build Tool**: Vite for fast development and optimized builds
- **Forms**: React Hook Form with Zod validation resolvers

The frontend follows a structured directory layout with components organized in `/components/ui/` for reusable UI elements and `/pages/` for route components. Path aliases are configured for clean imports using `@/` prefix.

## Backend Architecture

The backend uses Express.js with TypeScript in a simple, RESTful architecture:

- **Framework**: Express.js with TypeScript
- **Development**: tsx for TypeScript execution in development
- **Build**: esbuild for production bundling
- **Storage Interface**: Abstracted storage layer with in-memory implementation as default
- **Error Handling**: Centralized error middleware
- **Logging**: Custom request logging with response capture

The server is structured with a modular approach using route registration and storage abstraction patterns.

## Data Storage

The application uses a flexible storage architecture:

- **ORM**: Drizzle ORM for type-safe database interactions
- **Database**: PostgreSQL via Neon serverless driver
- **Schema**: Centralized schema definition in `/shared/schema.ts`
- **Migrations**: Drizzle Kit for database schema management
- **Storage Interface**: Abstract storage interface allowing for multiple implementations (currently includes in-memory storage for development)

## Database Schema

The current schema includes a basic user system:
- **users table**: Contains id (UUID), username (unique), and password fields
- **Validation**: Zod schemas for runtime validation of user data

## Authentication & Authorization

The application includes basic session infrastructure:
- **Sessions**: PostgreSQL session store with connect-pg-simple
- **Cookies**: Credential-based authentication setup
- **Storage Methods**: User creation and retrieval methods in storage interface

## Build & Development

The project uses a monorepo structure with shared code:
- **Development**: Concurrent frontend (Vite) and backend (tsx) development servers
- **Production**: Frontend builds to static assets, backend bundles with esbuild
- **Shared Code**: Common TypeScript definitions and schemas in `/shared/`
- **Environment**: Environment-based configuration with DATABASE_URL requirement

## External Dependencies

- **Database**: Neon PostgreSQL serverless database
- **UI Framework**: Radix UI primitives for accessible components
- **Styling**: Tailwind CSS with PostCSS processing
- **Icons**: Lucide React for consistent iconography
- **Animations**: Framer Motion for smooth animations and transitions
- **Date Handling**: date-fns for date utilities
- **Development Tools**: Replit-specific plugins for development environment integration