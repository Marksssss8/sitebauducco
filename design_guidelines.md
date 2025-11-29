# Design Guidelines: Bauducco-Inspired E-Commerce Platform

## Design Approach
**Reference-Based Design** inspired by premium food e-commerce brands (Bauducco, Ferrero, Lindt) combined with modern e-commerce best practices (Shopify stores, specialty food retailers). Focus on appetite appeal, warm hospitality, and frictionless purchasing.

## Core Design Principles
1. **Appetite Appeal First**: Product photography and recipes drive desire
2. **Warm Brazilian Hospitality**: Inviting, approachable, family-oriented
3. **Effortless Commerce**: Streamlined purchase flows, minimal friction
4. **Seasonal Excitement**: Bold promotional moments for holidays/campaigns

## Typography System

**Font Family**: Inter (via Google Fonts CDN)

**Hierarchy**:
- Hero Headlines: text-5xl md:text-6xl lg:text-7xl, font-semibold (600)
- Section Titles: text-3xl md:text-4xl, font-semibold (600)
- Product Names: text-xl md:text-2xl, font-semibold (600)
- Subheadings: text-lg md:text-xl, font-medium (500)
- Body Text: text-base, font-normal (400)
- Small Text/Labels: text-sm, font-normal (400)
- Micro Text: text-xs, font-normal (400)

**Line Heights**: leading-tight for headlines, leading-relaxed for body text

## Layout System

**Spacing Scale**: Use Tailwind units of **2, 4, 8, 12, 16, 20, 24** (e.g., p-4, gap-8, mb-12)

**Container Widths**:
- Full-width sections: w-full with max-w-7xl px-4 md:px-8
- Content sections: max-w-6xl mx-auto
- Text content: max-w-3xl
- Checkout flow: max-w-4xl

**Grid System**: 
- Product grids: grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 md:gap-6
- Recipe cards: grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8
- Feature sections: grid-cols-1 md:grid-cols-2 gap-12

**Section Spacing**: py-12 md:py-16 lg:py-20 for major sections

## Component Library

### Navigation & Header
- **Mega Menu**: Full-width dropdown with product categories, featured items, and recipe links
- **Search Bar**: Prominent placement, autosuggest with product thumbnails
- **Sticky Header**: Fixed on scroll with reduced height (h-20 → h-16)
- **Mobile Menu**: Full-screen overlay with category accordion

### Product Components
- **ProductCard**: Image (4:3 ratio), title, price, quick-add button, promo badge
- **ProductGallery**: Main image with thumbnail strip below, pinch-zoom on mobile
- **BuyBox**: Prominent variant selector, quantity stepper, large "Add to Cart" + "Buy Now" buttons
- **Nutritional Info Tabs**: Tabbed interface for description, nutrition facts, reviews, shipping

### Cart & Checkout
- **CartDrawer**: Slide-in from right, product thumbnails, quantity controls, subtotal
- **CheckoutSteps**: Horizontal progress bar with 4 steps, numbered indicators
- **AddressForm**: CEP lookup auto-fills address fields, validation states
- **ShippingOptions**: Radio cards with delivery time estimates and pricing

### Content Components
- **RecipeCard**: Hero image (16:9), prep time badge, difficulty level, CTA to full recipe
- **PromoBanner**: Full-width banners with background images, centered text overlays with blurred button backgrounds
- **NewsletterModal**: Center-screen modal with discount incentive, email input with inline validation
- **Toast Notifications**: Top-right corner, auto-dismiss, success/error states

### Promotional Elements
- **Hero Section**: Full-width image (min-h-[500px] md:min-h-[600px]), centered text with blurred-background CTAs
- **Seasonal Banners**: Top-of-page promotional strip, dismissible
- **Bundle Cards**: Multi-product display with combined pricing, "Save X%" badge

## Interaction Patterns

**Animations**: Use transition-all duration-300 for hover states, fade-in-up for scroll reveals (minimal, purposeful)

**Button States**:
- Primary CTA: Bold, high-contrast, scale-105 on hover
- Secondary: Outlined, hover fill
- Disabled: Reduced opacity, cursor-not-allowed

**Image Treatments**:
- Product cards: hover:scale-105 transform on image
- Recipe cards: Slight darkening overlay on hover
- Gallery: Smooth fade transitions between images

**Loading States**:
- Skeleton screens for product grids
- Spinner for checkout submission
- Progress indicators for multi-step flows

## Images

**Hero Image**: Large, appetite-appeal hero featuring seasonal product (panettone during holidays, cookies for everyday). Image should be warm, inviting, with natural lighting. Minimum 1920x800px, optimized WebP.

**Product Images**: High-quality product photography on white/cream backgrounds, 4:3 ratio, multiple angles in gallery. Show product texture and packaging.

**Recipe Images**: Finished dish photography, styled to show product incorporation. 16:9 ratio for card thumbnails, vertical images for recipe detail pages.

**Promotional Banners**: Lifestyle imagery showing products in family/celebration contexts. Full-width, optimized for text overlays.

**About Page**: Brand heritage imagery, timeline photos, production/quality shots.

**Image Placements**:
- Homepage: Hero banner, featured products grid, seasonal campaign section, recipe showcase
- Product pages: Main gallery (5-7 images), lifestyle shots showing usage
- Recipe pages: Hero image, step-by-step process shots
- Promotional pages: Full-bleed background images with content overlays

## Accessibility Implementation

- ARIA labels on all interactive elements
- Focus visible states with outline-offset-2
- Skip navigation link
- Alt text for all product/content images (decorative images: alt="")
- Color contrast minimum AA compliance
- Keyboard navigation throughout checkout flow
- Form validation with clear error messaging

## Mobile-First Considerations

- Touch targets minimum 44x44px
- Simplified navigation drawer
- Sticky add-to-cart on PDP (fixed bottom bar)
- One-column checkout on mobile
- Swipeable product galleries
- Collapsible filter panels