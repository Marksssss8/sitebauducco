# Bauducco E-Commerce Platform

## Overview

This is a premium Brazilian food e-commerce platform inspired by Bauducco, featuring institutional content, product catalog, recipes, and checkout flows. Built with modern web technologies focusing on performance, SEO, and user experience.

The application serves as a complete headless e-commerce solution with:
- Brand storytelling and institutional pages
- Product catalog with variants and promotions
- Recipe content hub
- Shopping cart and checkout flow
- Customer support and account management

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework**: React with TypeScript using Vite as the build tool

**Routing**: Wouter for lightweight client-side routing with SSR-like patterns

**State Management**:
- React Context API for global state (Cart, Theme)
- TanStack Query for server state and caching
- Local storage for cart persistence

**UI Component System**: 
- shadcn/ui components built on Radix UI primitives
- Tailwind CSS with custom design tokens matching Bauducco brand
- Component-based architecture with reusable primitives
- Design system follows "New York" style variant

**Design Philosophy**:
- Mobile-first responsive design
- Warm color palette (reds, creams) inspired by food e-commerce
- Inter font family via Google Fonts
- Appetite-driven visual hierarchy emphasizing product photography

### Backend Architecture

**Server Framework**: Express.js with TypeScript

**Architecture Pattern**: API-first with REST endpoints serving JSON

**Key Backend Components**:
- `/server/routes.ts` - API route definitions for products, recipes, cart, orders
- `/server/storage.ts` - In-memory data store with seed data (production would use database)
- `/server/static.ts` - Static file serving for production builds
- `/server/vite.ts` - Vite dev server integration for HMR in development

**Build Process**:
- Client: Vite builds React SPA to `dist/public`
- Server: esbuild bundles Express app to `dist/index.cjs`
- Selective bundling of dependencies to reduce cold start times

### Data Storage Solutions

**Current Implementation**: In-memory storage with TypeScript objects (`server/storage.ts`)

**Database Schema** (defined but not yet connected):
- Drizzle ORM configured for PostgreSQL
- Schema definitions in `shared/schema.ts` using Zod for validation
- Neon serverless PostgreSQL ready for integration
- Migration system configured via `drizzle.config.ts`

**Data Models**:
- Products (with variants, nutritional info, categories, tags)
- Recipes (with ingredients, steps, difficulty levels)
- Cart (items, totals, applied promos)
- Orders (customer info, shipping, payment)
- Promotions and promo pages
- Addresses, shipping options, payment methods

### Authentication and Authorization

**Current State**: Not yet implemented

**Planned Architecture**:
- Session-based auth with connect-pg-simple for session storage
- Password hashing with bcrypt or argon2
- Protected routes for account management and order history
- Guest checkout support

### External Dependencies

**Payment Providers** (referenced but not integrated):
- MercadoPago
- PagSeguro  
- PIX (Brazilian instant payment)
- Credit card tokenization for secure payments

**Search Engine** (referenced but not integrated):
- Algolia or Elasticsearch for product/recipe search
- Autosuggest functionality
- Faceted filtering

**Analytics**:
- Google Analytics 4 integration via gtag.js
- Event tracking for e-commerce (page views, add to cart, purchases)
- Configured via `VITE_GA_MEASUREMENT_ID` environment variable

**Content Management** (referenced but not integrated):
- Strapi or Contentful for headless CMS
- Would manage brand pages, recipes, banners, promotions

**CDN/Hosting** (referenced architecture):
- Vercel for frontend hosting
- Serverless functions for backend API
- Cloudflare or CloudFront for CDN

**UI Component Libraries**:
- Radix UI primitives (dialogs, dropdowns, tooltips, etc.)
- Embla Carousel for image galleries
- React Hook Form with Zod validation
- Lucide React for icons

**Styling**:
- Tailwind CSS with custom configuration
- PostCSS with autoprefixer
- CSS variables for theming (light/dark mode support)

**Development Tools**:
- TypeScript for type safety
- ESBuild for fast server bundling
- Vite plugins for Replit integration (dev banner, cartographer)

**Third-party Services Ready for Integration**:
- Email service (Nodemailer configured in dependencies)
- Image optimization/CDN
- Product reviews and ratings
- Inventory management system
- Shipping rate calculators
- Multi-domain setup (www, shop, promo subdomains)