# Bocage Champagne Bar

**Saratoga Springs' First Champagne Bar** | [bocage.vercel.app](https://bocage.vercel.app)

A full-stack web application for Bocage Champagne Bar — an intimate, 20-seat champagne bar at 10 Phila Street, Saratoga Springs, NY. Founded by Clark Gale & Zac Denham.

---

## Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, React Router v6, Tailwind CSS |
| Backend | Vercel Serverless Functions (Node.js) |
| Database | Supabase (PostgreSQL + Row Level Security) |
| Storage | Supabase Storage (CDN-backed image hosting) |
| Hosting | Vercel (auto-deploy from GitHub) |
| Icons | Lucide React |
| Fonts | Great Vibes, Cormorant Garamond, Montserrat |

## Features

### Public Site
- **Homepage** — Hero slideshow, about section, menu preview, hours, press scroll, testimonials
- **Menu** — 4 tabs (Food, Wines by the Glass, Flights/Cocktails/Beer, By the Bottle) with full real menu data
- **Wine Profile Cards** — Click any wine to see label image, region, vintage, grapes, tasting notes, and reserve CTA. Profiles stored in Supabase with Vivino label images.
- **Events** — Upcoming/past event listings with ticket links
- **Gallery** — Photo grid with real venue photography
- **Press** — 26 real press articles with Google favicon logos, horizontal scroll preview on homepage
- **Blog (Uncorked)** — 12 champagne-themed blog posts with share bar, related posts, tag system
- **Merch** — Product listings with Toast POS integration
- **Gift Cards** — Toast gift card integration
- **Private Events** — Venue info, capacity, features, inquiry form
- **Press Kit** — Downloadable press materials
- **Contact** — Contact form with Resend email integration

### Admin CMS (19 Editable Sections)
Full content management system accessible at `/admin` with password authentication.

| Section | Capabilities |
|---------|-------------|
| Hero Content | Eyebrow, title, subtitle, tagline, CTA labels |
| Hero Slides | Drag-and-drop image upload, alt text |
| About | Heading, body, owners, title |
| Team Profiles | Names, roles, photos (upload), bios, podcast links |
| Hours | Daily open/close times, override messages |
| Location | Address, phone, email, Google Maps URLs |
| Contact Emails | General, private events, press emails |
| Links & Social | Resy, Instagram, Facebook, Standard Fare |
| Menu Items | Full CRUD across all 4 menu categories |
| Events | Title, date, time, description, price, ticket URL |
| Private Events | Heading, body, capacity, features list |
| Gallery | Drag-and-drop photo upload, alt text, captions |
| Testimonials | Name, rating, source, review text |
| Google Rating | Rating score, review count |
| Press Coverage | Publication, headline, URL (auto-generates favicon logo) |
| Blog (Uncorked) | Full post editor with title, slug, body, tags, published/draft toggle |
| Merchandise | Name, price, description, image upload, variants, availability |
| Toast & Gift Cards | Order URL, gift card URL, restaurant ID |
| Settings | Preview mode toggle, admin/preview passwords |

### Data Persistence
- **Supabase PostgreSQL** — `site_data` table stores full CMS config as JSONB, `wine_profiles` table stores structured wine data with label images
- **Supabase Storage** — `images` bucket for admin-uploaded photos (hero, gallery, team, blog, merch) with CDN delivery
- **localStorage fallback** — Graceful degradation if Supabase is unreachable
- **Debounced sync** — Admin edits auto-save to Supabase (500ms debounce)

### Wine Profile System
- **Clickable wine items** on Wines by the Glass and By the Bottle tabs
- **Rich profile modal** with label image, producer, region, vintage, grapes, tasting notes, pricing
- **Supabase-backed** profiles with Vivino label images for key wines
- **Auto-parse fallback** — Wines without Supabase profiles parse their description string into structured data
- **"Reserve to Enjoy at Bocage"** CTA linking to Resy

## Project Structure

```
bocage/
├── api/                          # Vercel serverless functions
│   ├── contact-form.js           # Resend email integration
│   └── resy-availability.js      # Resy availability check
├── public/                       # Static assets
├── src/
│   ├── components/
│   │   ├── admin/
│   │   │   └── ImageUpload.jsx   # Drag-and-drop Supabase Storage upload
│   │   ├── layout/
│   │   │   ├── Footer.jsx        # Site footer with admin login modal
│   │   │   ├── Navbar.jsx        # Responsive navigation
│   │   │   └── PageLayout.jsx    # Shared page wrapper
│   │   ├── sections/             # Homepage sections
│   │   │   ├── AboutSection.jsx
│   │   │   ├── HeroSection.jsx
│   │   │   ├── HoursSection.jsx
│   │   │   └── ResyAvailability.jsx
│   │   ├── ui/
│   │   │   ├── ProfileCardModal.jsx
│   │   │   └── WineProfileModal.jsx  # Wine detail modal
│   │   ├── PreviewGate.jsx       # Password-protected preview mode
│   │   └── ScrollToTop.jsx
│   ├── context/
│   │   └── AdminContext.js       # Global state + Supabase sync
│   ├── data/
│   │   ├── siteData.js           # Default site content (750+ lines)
│   │   └── pressOutlets.js       # Press outlet registry
│   ├── hooks/
│   │   └── useWineProfiles.js    # Supabase wine profile fetch/cache
│   ├── lib/
│   │   └── supabase.js           # Supabase client
│   ├── pages/
│   │   ├── AdminPage.jsx         # Full CMS dashboard (700+ lines)
│   │   ├── BlogPage.jsx          # Uncorked blog listing
│   │   ├── BlogPostPage.jsx      # Individual blog post with share bar
│   │   ├── ContactPage.jsx
│   │   ├── EventsPage.jsx
│   │   ├── GalleryPage.jsx
│   │   ├── GiftCardsPage.jsx
│   │   ├── HomePage.jsx          # Homepage with all sections
│   │   ├── MenuPage.jsx          # Tabbed menu with wine profile modals
│   │   ├── MerchPage.jsx
│   │   ├── NotFoundPage.jsx
│   │   ├── PressKitPage.jsx
│   │   ├── PressPage.jsx
│   │   └── PrivateEventsPage.jsx
│   ├── App.js                    # Router configuration
│   └── index.js                  # Entry point
├── tailwind.config.js            # Custom Bocage theme
└── package.json
```

## Environment Variables

| Variable | Description |
|----------|-------------|
| `REACT_APP_SUPABASE_URL` | Supabase project URL |
| `REACT_APP_SUPABASE_ANON_KEY` | Supabase anonymous public key |
| `REACT_APP_PREVIEW_PASSWORD` | Preview gate password (fallback) |
| `RESEND_API_KEY` | Resend email API key (serverless functions) |

## Supabase Schema

```sql
-- CMS content storage
site_data (id INT PK, data JSONB, updated_at TIMESTAMPTZ)

-- Wine profile cards
wine_profiles (id UUID PK, wine_name, producer, region, appellation,
               grapes TEXT[], vintage, tasting_notes, label_image_url,
               price_glass, price_bottle, menu_key, section_title,
               reserve_url, created_at, updated_at)

-- Storage buckets
images (public) — hero/, gallery/, team/, blog/, merch/
```

## Development

```bash
npm install
PORT=3001 npm start      # Dev server on localhost:3001
npm run build            # Production build
```

## Deployment

Auto-deploys to Vercel on `git push origin main`.

```bash
git add -A && git commit -m "Your message" && git push origin main
```

## Design System

| Token | Hex | Usage |
|-------|-----|-------|
| `champagne` | `#C4A35A` | Primary accent, CTAs, highlights |
| `ivory` | `#FAF8F5` | Backgrounds |
| `charcoal` | `#2A2A28` | Text, dark sections |
| `silver` | `#9A9A98` | Secondary text |
| `rose` | `#C4727F` | Alerts, errors |

**Fonts:** Great Vibes (script/logo), Cormorant Garamond (display/headings), Montserrat (body)

## Real Menu Data

Complete Bocage Winter 2025 menu sourced from official PDFs:
- 9 sparkling wines by the glass (including Bocage Everyday Cuvee — the wedding wine)
- 5 champagnes by the glass (including Drappier Les Riceys exclusive to Bocage)
- 12 still wines (white, rose/skin contact, red)
- 8 signature cocktails, 2 beers, 2 flights
- 17 grower champagnes by the bottle
- 19 prominent houses (Dom Perignon, Krug, Cristal, Salon Le Mesnil at $2,000)
- 11 rare & exquisite vintage selections (back to 1978)
- 5 large format bottles
- Full food menu (bar snacks, caviar, something more, something sweet)

---

**Sure Thing Hospitality** | Clark Gale & Zac Denham | Saratoga Springs, NY

Website created by [Cole Levy](https://www.linkedin.com/in/colelevy/)
