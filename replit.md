# Medical Clinic Knowledge Base System

## Overview

This is a full-stack web application built for managing a medical clinic's knowledge base. The system provides an organized way to store, retrieve, and manage medical procedures, protocols, scripts, and frequently asked questions across different departments and functions.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Styling**: Tailwind CSS with custom medical-themed color variables
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js server
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **API**: RESTful API with structured endpoints
- **Session Management**: PostgreSQL session store
- **Development**: Hot reload with Vite middleware integration

## Key Components

### Database Schema
- **Users Table**: Basic user authentication with username/password
- **Knowledge Base Content Table**: Structured content with sections, subsections, titles, content, tags, and metadata
- **Content Organization**: Hierarchical structure with predefined sections (call-tracker, qcm-measures, scripts, faq, evelyn)

### API Endpoints
- `GET /api/knowledge-base` - Retrieve all content or filter by section/subsection
- `GET /api/knowledge-base/:id` - Get specific content by ID
- `POST /api/knowledge-base` - Create new content
- `PUT /api/knowledge-base/:id` - Update existing content
- `DELETE /api/knowledge-base/:id` - Delete content
- `GET /api/knowledge-base/search/:query` - Search content

### Frontend Components
- **Sidebar Navigation**: Organized by medical departments and functions
- **Content Cards**: Display knowledge base entries with visual indicators
- **Content Editor**: Rich text editing with tags and metadata
- **Search Bar**: Real-time search with results preview
- **Responsive Design**: Mobile-friendly interface

## Data Flow

1. **Content Creation**: Users create content through the editor interface
2. **Validation**: Client-side validation with Zod schemas, server-side validation
3. **Storage**: Content stored in PostgreSQL with proper indexing
4. **Retrieval**: Content fetched via REST API with query-based filtering
5. **Caching**: Client-side caching with React Query for optimal performance
6. **Real-time Updates**: Automatic cache invalidation on content changes

## External Dependencies

### Core Dependencies
- **Database**: Neon Database (serverless PostgreSQL)
- **UI Framework**: Radix UI primitives for accessible components
- **Development Tools**: Replit integration for cloud development
- **Build Tools**: Vite, esbuild for production builds

### Key Libraries
- **drizzle-orm**: Type-safe database operations
- **@tanstack/react-query**: Server state management
- **react-hook-form**: Form handling and validation
- **zod**: Schema validation
- **tailwindcss**: Utility-first CSS framework
- **wouter**: Lightweight routing

## Deployment Strategy

### Development
- **Environment**: Replit cloud development environment
- **Hot Reload**: Vite development server with Express middleware
- **Database**: Neon Database with environment-based configuration
- **Build**: TypeScript compilation with strict mode enabled

### Production
- **Build Process**: Vite builds client assets, esbuild bundles server code
- **Static Assets**: Served from `/dist/public` directory
- **Database**: Production PostgreSQL connection via DATABASE_URL
- **Session Storage**: PostgreSQL-based session management

### Environment Configuration
- `NODE_ENV`: Development/production environment flag
- `DATABASE_URL`: PostgreSQL connection string (required)
- `REPL_ID`: Replit-specific configuration for development features

## Changelog

- July 07, 2025. Initial setup
- July 07, 2025. Rebuilt knowledge base structure with custom sections:
  - Call Tracker with interactive table for insurance call tracking
  - QCM Measures with search functionality and detailed measure information
  - Scripts section with VM and client attraction subsections
  - FAQ section with general and insurance coverage subsections
- July 07, 2025. Added complete HealthFirst QCM measures (24 measures) including preventive care, chronic disease management, pediatric care, and mental health measures
- July 07, 2025. Added complete FidelisCare QCM measures (28 measures) including all HealthFirst measures plus additional specialized measures for heart attack follow-up, diabetes complications, and readmission prevention
- July 07, 2025. Added complete UnitedHealthCare QCM measures (27 measures) with detailed eCW location information and appointment scheduling guidance
- July 07, 2025. Implemented color-coded insurance system: Blue for HealthFirst, Green for FidelisCare, Purple for UnitedHealthCare
- July 07, 2025. Added reminders section to sidebar with bilingual content and insurance company badges

## User Preferences

Preferred communication style: Simple, everyday language.