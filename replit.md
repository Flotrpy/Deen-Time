# Deen Time - Islamic Prayer Companion

## Overview

Deen Time is a full-stack Islamic prayer companion application built with a modern web stack. It provides prayer times, Quran reading, hadith of the day, masjid finder, Islamic calendar, and prayer tracking features. The application follows a monorepo structure with separate client and server directories and shared schema definitions.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized production builds
- **UI Framework**: Radix UI components with Shadcn/ui styling system
- **Styling**: Tailwind CSS with custom theme configuration
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Maps**: Leaflet for interactive map functionality

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM for type-safe database operations
- **Database**: PostgreSQL with Neon serverless adapter
- **Session Management**: PostgreSQL-based session storage using connect-pg-simple

### Development Setup
- **Development Server**: Custom Vite middleware integration with Express
- **Build Process**: Separate client (Vite) and server (esbuild) builds
- **Hot Reload**: Vite HMR for frontend, tsx for backend development

## Key Components

### Database Schema
Located in `shared/schema.ts`, defines the following entities:
- **Masjids**: Mosque locations with coordinates
- **Events**: Islamic events and gatherings
- **Notifications**: Prayer notification preferences per user
- **Surahs**: Quran chapters with metadata
- **Verses**: Individual Quran verses with Arabic text and translations
- **Prayer Tracking**: Daily prayer completion tracking
- **Achievements**: User achievement system

### API Layer
RESTful API endpoints in `server/routes.ts`:
- Masjid CRUD operations
- Event management
- Prayer tracking and streak calculation
- Notification settings
- Achievement system

### Frontend Pages
- **Home**: Dashboard with prayer times and Ramadan countdown
- **Quran**: Embedded Quran.com iframe for reading
- **Hadith**: Daily hadith display with rotation logic
- **Duas**: Collection of Islamic supplications
- **Masjids**: Interactive map for finding nearby mosques
- **Events**: Community event management
- **Friday Prayers**: Specific Jummah prayer information

### Prayer Times Integration
- External API integration for accurate prayer times
- Location-based calculations using ZIP codes
- Sunrise/sunset time tracking
- Prayer completion tracking with streak counting

## Data Flow

1. **Client Requests**: Frontend makes API calls using TanStack Query
2. **Server Processing**: Express routes handle requests and validate data using Zod schemas
3. **Database Operations**: Drizzle ORM performs type-safe database queries
4. **Response**: JSON data returned to client and cached by React Query
5. **UI Updates**: React components re-render based on query state changes

## External Dependencies

### Third-Party Services
- **Prayer Times API**: External service for accurate Islamic prayer times
- **OpenCage Geocoding**: Location services for address-to-coordinate conversion
- **Quran.com**: Embedded iframe for Quran reading
- **Hijri Date API**: Custom endpoint for Islamic calendar conversion

### Key Libraries
- **@neondatabase/serverless**: PostgreSQL serverless connection
- **@radix-ui/***: Headless UI components
- **leaflet**: Interactive maps
- **date-fns**: Date manipulation utilities
- **zod**: Runtime type validation
- **wouter**: Lightweight routing

## Deployment Strategy

### Build Process
- **Frontend**: Vite builds optimized static assets to `dist/public`
- **Backend**: esbuild bundles server code to `dist/index.js`
- **Database**: Drizzle migrations in `migrations/` directory

### Environment Configuration
- **DATABASE_URL**: PostgreSQL connection string (required)
- **VITE_OPENCAGE_API_KEY**: Geocoding service API key (optional)

### Production Setup
- Single Node.js process serves both API and static files
- Express serves built frontend assets in production
- Database migrations applied via `drizzle-kit push`

### Development vs Production
- **Development**: Vite dev server with HMR, tsx for backend watching
- **Production**: Static file serving with optimized builds
- **Database**: Same PostgreSQL setup for both environments

The application is designed to be deployed on platforms like Replit, Vercel, or any Node.js hosting service with PostgreSQL database support.