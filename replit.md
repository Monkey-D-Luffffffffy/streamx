# StreamX - Video Streaming Platform

## Overview

StreamX is a modern video streaming platform built with React, Express.js, and Drizzle ORM. The application provides a Netflix-like interface for streaming video content hosted on Google Drive, featuring content categorization, search functionality, and a responsive user interface.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **Styling**: Tailwind CSS with shadcn/ui component library
- **Build Tool**: Vite for fast development and optimized builds
- **UI Components**: Comprehensive component library using Radix UI primitives

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Design**: RESTful API endpoints for content management
- **Development**: Hot reload with Vite middleware integration

### Data Storage Solutions
- **Database**: PostgreSQL configured via Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **ORM**: Drizzle ORM with TypeScript schema definitions
- **Migrations**: Drizzle Kit for database schema management
- **Session Storage**: PostgreSQL-based sessions using connect-pg-simple

## Key Components

### Database Schema
The application uses two main tables:
- **Content Table**: Stores video metadata including title, description, year, genre, type, category, thumbnail URLs, and Google Drive URLs
- **Watchlist Table**: Manages user watchlists with user-content relationships

### Frontend Components
- **Navigation**: Responsive navbar with search functionality and mobile support
- **Video Player**: Custom video player component with Google Drive iframe integration
- **Content Grid**: Reusable component for displaying content collections
- **Content Cards**: Individual content display components with metadata
- **Hero Section**: Featured content showcase with call-to-action buttons

### API Endpoints
- `GET /api/content` - Retrieve all content
- `GET /api/content/:id` - Get specific content by ID
- `GET /api/content/category/:category` - Filter content by category
- `GET /api/content/type/:type` - Filter content by type
- `GET /api/search` - Search content functionality
- Watchlist management endpoints (create, read, delete)

## Data Flow

1. **Content Serving**: Video files are hosted on Google Drive and embedded via iframe
2. **Metadata Management**: Content information stored in PostgreSQL database
3. **Client Requests**: React frontend makes API calls using TanStack Query
4. **Server Processing**: Express.js server handles requests and database operations
5. **Response Caching**: Query client provides intelligent caching and background updates

## External Dependencies

### Core Dependencies
- **Database**: @neondatabase/serverless for PostgreSQL connectivity
- **ORM**: drizzle-orm and drizzle-zod for type-safe database operations
- **UI Framework**: Extensive Radix UI component collection
- **Styling**: Tailwind CSS with custom design tokens
- **Query Management**: @tanstack/react-query for server state
- **Form Handling**: react-hook-form with @hookform/resolvers

### Development Tools
- **Build System**: Vite with React plugin
- **TypeScript**: Full TypeScript support across frontend and backend
- **Development Experience**: Replit-specific plugins for enhanced development

## Deployment Strategy

### Development Environment
- **Hot Reload**: Vite development server with Express.js middleware integration
- **Database**: Neon serverless PostgreSQL with environment-based configuration
- **Asset Serving**: Vite handles static assets and React application serving

### Production Build
- **Frontend**: Vite build process outputs optimized static assets
- **Backend**: esbuild bundles server code for Node.js deployment
- **Database**: Production PostgreSQL connection via DATABASE_URL environment variable
- **Static Serving**: Express.js serves built React application in production

### Recent Changes
- Removed admin panel interface based on user feedback
- Implemented file-based content management system
- Created easy-to-edit `server/content-data.ts` for content management
- Added comprehensive content management guide (`CONTENT_MANAGEMENT.md`)
- Reduced animation intensity for better user experience
- Simplified architecture by removing admin CRUD operations

### Key Architectural Decisions

1. **Google Drive Integration**: Chosen for free video hosting and reliable streaming capability
2. **File-Based Content Management**: Simple `content-data.ts` file for easy content editing without admin interface
3. **Drizzle ORM**: Selected for type safety and PostgreSQL-first approach
4. **TanStack Query**: Implemented for robust client-side state management and caching
5. **shadcn/ui**: Adopted for consistent, accessible UI components
6. **Monorepo Structure**: Shared schema between client and server for type consistency
7. **Vite Integration**: Used for both development experience and production builds