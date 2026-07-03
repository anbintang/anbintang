# Hello! I'm Anugrah Bintang Pria Sembada 👋

A Full-Stack Developer with **1+ year of production experience** building SPA-based web applications using **JavaScript, Laravel, React, and Vue.js**.  
Comfortable operating in real-world systems with real users, real constraints, and real deadlines — from national-scale government platforms to multi-tenant SaaS products.

I focus on shipping maintainable features, improving performance, writing reliable tests, and collaborating effectively within cross-functional engineering teams.

---

## Tech Stack

**Frontend**
- JavaScript / TypeScript (ES6+), SPA Architecture
- React 19 + Inertia.js (production)
- Vue.js 2 (Vuex, Vue Router)
- Tailwind CSS, shadcn/ui, Bootstrap
- React Hook Form, Zod, TanStack Query
- Responsive & cross-browser UI from Figma

**Backend & API**
- Laravel 8–13 (API, auth, business logic, queues, notifications)
- RESTful APIs & session-based JSON APIs
- PostgreSQL, MySQL
- Multi-tenancy (host-based), role/permission systems (Laratrust)
- Payment gateways (Midtrans, PrismaLink), wallet systems
- Laravel AI + pgvector (chatbot RAG)
- Pest / PHPUnit for automated testing
- Basic security & performance practices

**Tooling & DevOps**
- Node.js, pnpm, Vite, Webpack / Laravel Mix
- ESLint, Prettier, Laravel Pint
- Git & GitLab / GitHub (PRs, code reviews)
- Docker & Docker Compose (basic)
- CI/CD basics (GitLab CI)
- Cloudflare (DNS, tunnel for local webhook testing)

---

## Projects

### 1. **3D Web Developer Portfolio (In Progress)**  
A modern, interactive **3D web portfolio** designed to showcase projects, skills, and professional experience through motion and storytelling.  
This project explores combining traditional UI with real-time 3D graphics and smooth animations to create an immersive developer experience.

#### What I Learned from This Project
- Structuring a **React application** with reusable and scalable components
- Using **Vite** for faster development cycles and optimized builds
- Integrating **Three.js** into React to render and manage 3D scenes in the browser
- Understanding camera control, lighting, and object composition in real-time 3D
- Creating smooth, timeline-based animations using **GSAP**
- Coordinating UI animations with 3D object interactions
- Balancing **visual richness and performance**, especially on lower-end devices
- Shifting from page-based layouts to **experience-driven interfaces**

**Tech Stack:** Three.js, React Three Fiber, Drei, GSAP, Tailwind CSS, Vite, React 19  
**Status:** In Progress

---

### 2. **TravelBoost** — Multi-Tenant Travel SaaS Platform  
[TravelBoost](https://travelboost.co.id) is a **production multi-tenant travel platform** that connects travel agents, vendors, affiliates, and end-customers in a single Laravel + Inertia + React codebase. The system supports agent landing pages (subdomains & custom domains), vendor tour catalogs, end-to-end booking workflows, online/manual payments, wallets, AI chatbot, and platform administration.

As a full-stack developer on the team, I owned and shipped features across the full booking lifecycle, customer-facing agent subdomains, vendor/agent dashboards, payment integrations, AI chatbot, and Lighthouse-driven performance improvements — always backed by Pest feature tests and deployed to staging/production servers.

#### Key Features I Built & Improved

**End-to-End Booking Flow (All User Types)**
- Built and maintained the complete booking journey for **customers, agents, and vendors** — from tour selection and seat reservation through travel document upload, payment, and confirmation
- Multi-step booking wizard: guest details → room assignment → travel documents (passport/visa) → payment
- Reservation hold system with automatic expiry, down payment / full payment flows, and manual payment approval workflow
- Travel document management: passport fields (including place of issue), visa type selection, scan uploads, and platform-managed upload guide PDF
- Booking status lifecycle across `booking reserved`, `awaiting payment`, `down payment`, `full payment`, `expired`, and `cancelled`

**Customer Experience on Agent Subdomains**
- Tour catalog browsing on `{agent}.travelboost.co.id/tours` with schedule availability and pricing
- **My Bookings** dashboard with tabbed views: Current Bookings, Booking History, **Liked Tours** (favorites), and **Waiting List**
- Waiting list enrollment with priority selection, deadline-aware validation, and offer-to-booking conversion flow
- Customer profile management, invoice download, and session isolation per agent subdomain
- Liked-tours persistence and catalog indicators for authenticated customers

**Vendor & Agent Dashboard — Booking Operations (CRUD)**
- Full booking management index with search, filters, status badges, and row-level actions
- **Refund** processing with approval workflow and payment reconciliation
- **Reschedule** with price adjustment, customer notification, and payment status reconciliation (FP → DP on price increase)
- **Waiting list** management: queue view, schedule offering, priority reordering, status updates, and automated offer expiry
- Payment approval popup with manual payment proof display
- Dashboard hold-expiry resolution and booking correction flows

**Payment Integrations (Midtrans & PrismaLink)**
- **Midtrans** Snap integration for online payments with webhook-driven status sync and scheduled expiry jobs
- **PrismaLink** alternative gateway with backend/frontend callbacks, reusable payment attempts, and configurable validity windows (hours/minutes for UAT)
- Manual payment workflow: customer upload proof → vendor approval → confirmation email with invoice PDF
- Wallet top-up flows with auto-refresh after successful payment
- Payment confirmation emails with invoice/proforma PDF attachments and scheduled deadline reminders

**AI Chatbot**
- Maintained and improved the **Laravel AI chatbot** with tool-based booking assistance (tour search, schedule lookup, price quotes, reservation)
- Fixed chatbot auth context so agent/vendor dashboard users are not incorrectly told to log in as customers
- Diagnosed and addressed chatbot booking flow gaps (e.g. visa category selection required by backend but not exposed to AI tools)
- Chatbot settings, AI credit billing, streaming responses, and knowledge-base RAG integration

**Lighthouse & Performance Optimization**
- Improved **LCP and Speed Index** on marketing home, Puck tenant microsites, and affiliate landing pages
- Server-side hero image preload via `PerformanceHints` / `TenantLandingPreload` from Puck `landing_page_data`
- WebP image optimization, responsive `srcSet` in Puck editor, and `OptimizedImage` components
- Deferred non-critical client boot (Echo, payment services) on public marketing routes
- Optimized vendor **bookings index** (`/bookings`): deferred follow-up summary, lazy-loaded row actions/dialogs, debounced search, and reduced TTFB
- Fixed subdomain asset loading (`ViteAssetUrl`) and CSP hardening for S3/CDN previews, YouTube/Vimeo embeds, and Midtrans iframes

**Platform Reliability & Multi-Tenancy**
- `ScopeSessionToHost` middleware — isolates Laravel sessions per subdomain
- Vendor Package-1 Gate — per-vendor control over Basic Subscription agent access
- Platform documents admin (superadmin-managed PDF guides)
- `CheckUserStatus` middleware null-safety and tour create flow reliability fixes

#### What I Learned from This Project
- Owning a **full booking lifecycle** across multiple user roles — customer subdomain, agent dashboard, and vendor dashboard — in a single multi-tenant codebase
- Integrating **two payment gateways** (Midtrans + PrismaLink) with webhooks, manual approval flows, PDF invoicing, and scheduled payment reminders
- Building and debugging **customer-facing subdomain features** (catalog, liked tours, waiting list, my bookings) with host-scoped sessions and tenant-aware data
- Implementing **vendor-side CRUD operations** for bookings, refunds, reschedules, and waiting lists with complex business rules and status reconciliation
- Working with **AI chatbot tool orchestration** — auth context, booking reservation via chat, visa/passport data gaps, and streaming responses
- Driving **Lighthouse performance improvements** systematically: LCP preload, WebP assets, deferred Inertia props, JS code-splitting, and backend query optimization
- Writing **Pest feature tests first** (TDD) for controllers, services, middleware, notifications, and multi-step booking flows
- Collaborating in a team using conventional commits, PR reviews, and staged deploys to dev/production servers

**Tech Stack:** Laravel 13, PHP 8.5, Inertia.js v2, React 19, TypeScript, PostgreSQL, Tailwind CSS v4, Pest, Midtrans, PrismaLink, Laravel AI, Laravel Reverb, S3 (Neo), Caddy, Cloudflare  
**Website:** [https://travelboost.co.id](https://travelboost.co.id)

---

### 3. Amdalnet (Ministry of Environment of Indonesia)
AMDALNet is a **national-scale environmental approval platform** used to manage and process environmental feasibility documents across Indonesia.  
The system supports end-to-end workflows for project registration, document verification, assessment, and decision-making, enabling faster, more transparent, and standardized environmental permitting.

In this project, I worked on developing and maintaining SPA-based features, implementing workflow-driven business logic, optimizing performance, and integrating RESTful APIs within a large collaborative engineering team.

**Tech Stack:** Laravel, Vue.js, JavaScript, PostgreSQL, REST API, Node.js (tooling), GitLab, Docker  
**Website:** [https://amdalnet.kemenlh.go.id/#/](https://amdalnet.kemenlh.go.id/#/)

---

### 4. Nakula Sadewa Web-Based Tourism Information Center
Nakula Sadewa is a web-based tourism information center managed by the Trenggalek Regency Tourism and Culture Office. The website features a unique Travel Calculator that helps tourists estimate their trip expenses. This project is a collaboration between the Vocational Faculty of Universitas Brawijaya and the Trenggalek Tourism Office, supporting Trenggalek's vision as a sustainable tourism city. Nakula Sadewa enhances tourist services accessibility and promotes Trenggalek's tourism potential to a wider market.

**Tech Stack:** HTML, CSS, JavaScript, Bootstrap, Laravel (PHP), Blade, MySQL, Figma  
**Website:** [https://pesonawisata.trenggalekkab.go.id/](https://pesonawisata.trenggalekkab.go.id/)  
**Repository:** [GitHub](https://github.com/anbintang/nakula-sadewa.git)

---

## Contact
- Email: anugrahbintangps@gmail.com  
- LinkedIn: [linkedin.com/in/anugrahbintangps](https://linkedin.com/in/anugrahbintangps/)

---

Thanks for coming by! 😊
