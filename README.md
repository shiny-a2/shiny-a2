# Amirali Yaghouti

Senior WordPress / WooCommerce Performance & Infrastructure Engineer

I work on production commerce systems where WordPress is not only a CMS, but the operating surface for catalog performance, checkout reliability, background jobs, internal tools, reporting, CRM workflows, and technical SEO.

My strongest work is in WooCommerce performance engineering, MU-plugin architecture, database pressure reduction, controlled REST/API design, Action Scheduler tuning, admin operations tooling, and CRM/customer operation systems.

Portfolio: https://amiraliyaghouti.com  
LinkedIn: https://www.linkedin.com/in/amirali-yaghouti  
Email: amiraliyaghouti@gmail.com

## Engineering Identity

I am not positioning myself as a theme customizer or general WordPress freelancer. The work I want to be reviewed for is production engineering around live commerce platforms:

- diagnosing slow routes, queue pressure, transient growth, and cache misses;
- designing small, controlled plugin/MU-plugin modules instead of risky broad rewrites;
- building admin and operator tools that reduce manual work without weakening data integrity;
- keeping public code samples curated, anonymized, and safe to inspect.

## Infrastructure & Performance Focus

| Area | Production concern | Engineering response |
|---|---|---|
| Product detail pages | High TTFB from Elementor/WooCommerce load | guest-safe microcache, invalidation boundaries, request guards |
| Product archives | Slow filters and expensive catalog queries | cache-aware filters, fallback rendering, query reduction |
| REST/API traffic | Anonymous route pressure and expensive product reads | REST shielding, snapshot APIs, allowlists, rate controls |
| Background jobs | Action Scheduler backlog and admin instability | bounded cleanup, concurrency control, scheduled maintenance |
| Database boot cost | transient and autoload growth | transient guards, option audits, controlled cleanup |
| Admin operations | exceptional order and stock workflows | scoped admin tools, capability checks, audit notes, rollback thinking |

## Selected Production Impact

These metrics are used only where they are represented in the public website/resume materials.

- Product detail page TTFB: 2.3s -> 0.9s
- Product archive p95: 5.2s -> 1.7s
- REST route p95: 2.8s -> 0.9s
- Product API p95: 1.9s -> 0.42s
- Similar-products block render: 1.9s -> 0.42s
- Action Scheduler pending queue: about 38k -> about 4.9k
- Transient rows: about 1.3M -> about 180k
- Cart noise: about 4100/day -> about 180/day

## Featured Engineering Case Studies

### WooCommerce Performance Lab

https://github.com/shiny-a2/a2-woocommerce-performance-lab

Microcache boundaries, REST route control, Action Scheduler cleanup, transient protection, autoload hygiene, and low-overhead diagnostics for WooCommerce stores under real traffic pressure.

### CRM Operations System

https://github.com/shiny-a2/a2-crm-operations-system

WordPress-based CRM architecture for operator inboxes, customer follow-up, customer hubs, SMS/VoIP integration boundaries, reporting, and operational auditability.

### Style DNA Similar Products

https://github.com/shiny-a2/a2-style-dna-similar-products

Recommendation architecture using product signatures, cached candidate scoring, rebuild locks, and render-time protection for WooCommerce product pages.

### WooCommerce Admin Ops Toolkit

https://github.com/shiny-a2/a2-woocommerce-admin-ops-toolkit

Admin operation patterns for exceptional order workflows, operational flags, controlled edits, audit notes, and rollback-aware productivity tooling.

### Watch Marketplace Showcase

https://github.com/shiny-a2/a2-watch-marketplace-showcase

Architecture showcase for seller intake, verification states, custody/delivery flows, operator review, and marketplace workflow boundaries. Production launch is not represented.

## Technical Notes

### WooCommerce Performance

- [Request classification before cache](https://github.com/shiny-a2/a2-woocommerce-performance-lab/blob/main/docs/engineering-notes/request-classification-before-cache.md)
- [Action Scheduler backlog as operational risk](https://github.com/shiny-a2/a2-woocommerce-performance-lab/blob/main/docs/engineering-notes/action-scheduler-backlog-as-operational-risk.md)
- [Transient growth and autoload pressure](https://github.com/shiny-a2/a2-woocommerce-performance-lab/blob/main/docs/engineering-notes/transient-growth-and-autoload-pressure.md)

### Operational CRM Systems

- [Operator inbox state boundaries](https://github.com/shiny-a2/a2-crm-operations-system/blob/main/docs/engineering-notes/operator-inbox-state-boundaries.md)
- [Provider abstraction for SMS and VoIP](https://github.com/shiny-a2/a2-crm-operations-system/blob/main/docs/engineering-notes/provider-abstraction-for-sms-and-voip.md)

### Product Recommendation Systems

- [Recommendation without heavy real-time queries](https://github.com/shiny-a2/a2-style-dna-similar-products/blob/main/docs/engineering-notes/recommendation-without-heavy-real-time-queries.md)

### Admin Operations

- [Safe admin actions and rollback thinking](https://github.com/shiny-a2/a2-woocommerce-admin-ops-toolkit/blob/main/docs/engineering-notes/safe-admin-actions-and-rollback-thinking.md)

### Marketplace Architecture

- [Marketplace state machine before payments](https://github.com/shiny-a2/a2-watch-marketplace-showcase/blob/main/docs/engineering-notes/marketplace-state-machine-before-payments.md)

## Architecture Specialization Areas

- WooCommerce request lifecycle and cache safety
- MU-plugin architecture for small, reversible production changes
- REST/API route pressure reduction and snapshot data patterns
- MySQL option/transient pressure management
- Action Scheduler and WP-Cron maintenance
- Admin UX for operations teams
- CRM/customer operation workflows
- Technical SEO architecture for catalog-heavy sites
- Human-reviewed automation with n8n, Google Sheets, and reporting workflows

## Operational Tooling Highlights

- lightweight performance logging that avoids storing customer data;
- scheduled cleanup routines with bounded batches;
- admin-only operations tools with capability checks and audit notes;
- snapshot/rebuild patterns for expensive product data;
- provider abstractions for SMS/VoIP-style integrations;
- rollback and fallback thinking for checkout/admin-sensitive changes.

## CRM & Internal Systems

I build internal systems as operational tools, not as generic dashboards. The recurring concerns are assignment state, customer context, role boundaries, reporting quality, provider failure, auditability, and whether the tool makes daily work safer instead of just prettier.

## Current Engineering Focus

- hardening WooCommerce performance case studies into public-safe technical references;
- improving public samples so reviewers can see architecture without seeing private business logic;
- keeping production repositories private where direct release would expose clients, operations, or implementation details;
- aligning GitHub, portfolio, and resume around senior production ownership.

## Engineering Principles

- Measure the bottleneck before changing the system.
- Prefer reversible modules over broad rewrites on live commerce platforms.
- Treat cache invalidation, checkout state, and customer data as first-class constraints.
- Keep public code curated and safe; never publish raw production dumps.
- Write documentation that explains tradeoffs, not just features.
