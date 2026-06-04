# Amirali Yaghouti

Full-Stack Commerce & Platform Engineer

I work on production commerce systems where the important work spans backend PHP, WordPress/WooCommerce, frontend UX, APIs, data workflows, CRM operations, automation, reporting, and technical SEO.

My strongest work is turning business operations into reliable web systems: fast storefronts, controlled internal tools, snapshot APIs, CRM workflows, reporting pipelines, automation boundaries, and public-safe architecture documentation.

Portfolio: https://amiraliyaghouti.com  
LinkedIn: https://www.linkedin.com/in/amirali-yaghouti  
Email: amiraliyaghouti@gmail.com

## Public Reviewer Path

For a fast hiring review, use the website for the broader career story and this GitHub profile for technical proof:

- Website overview: https://amiraliyaghouti.com
- Project index: https://amiraliyaghouti.com/projects.html
- Case-study library: https://amiraliyaghouti.com/case-studies.html
- GitHub samples: start with the six repositories below.

The public repositories are curated showcases. They include architecture notes, public-safe PHP samples, and sample-only syntax checks. They do not expose private implementation code or production data.

## Technical Writing

- [Public technical writing index](docs/technical-writing/index.md)
- [WooCommerce request classification before cache](docs/technical-writing/articles/woocommerce-request-classification-before-cache.md)
- [Action Scheduler backlog as operational risk](docs/technical-writing/articles/action-scheduler-backlog-operational-risk.md)
- [Public-safe engineering proof](docs/technical-writing/articles/public-safe-engineering-proof.md)

## Start Here

- Commerce platform modernization, architecture, data modeling, and migration planning: [commerce-platform-modernization-showcase](https://github.com/shiny-a2/commerce-platform-modernization-showcase)
- WooCommerce performance, cache boundaries, REST pressure, and scheduler risk: [a2-woocommerce-performance-lab](https://github.com/shiny-a2/a2-woocommerce-performance-lab)
- CRM, operator workflows, provider boundaries, and reporting snapshots: [a2-crm-operations-system](https://github.com/shiny-a2/a2-crm-operations-system)
- Automation workflows, n8n-style routing, reporting pipelines, and approval gates: [commerce-automation-workflows-showcase](https://github.com/shiny-a2/commerce-automation-workflows-showcase)
- Retail operations PWA architecture and assisted ordering workflows: [jeweltimeco-showcase](https://github.com/shiny-a2/jeweltimeco-showcase)
- Marketplace state design, custody boundaries, and review workflows: [a2-watch-marketplace-showcase](https://github.com/shiny-a2/a2-watch-marketplace-showcase)

## Engineering Identity

I am not positioning myself as a theme customizer or generic freelancer. The work I want to be reviewed for is full-stack production engineering around commerce and operations platforms:

- diagnosing slow routes, queue pressure, transient growth, and cache misses;
- designing small, controlled plugin/MU-plugin modules instead of risky broad rewrites;
- building admin and operator tools that reduce manual work without weakening data integrity;
- connecting APIs, spreadsheets, CRM events, messaging providers, and reporting workflows safely;
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

## Infrastructure Thinking

- Classify request type before applying cache, API controls, or shortcuts.
- Treat cache invalidation as part of the design, not a cleanup task.
- Watch queue backlog and oldest pending age as operational risk signals.
- Control REST/API pressure separately from page-render performance.
- Design admin operations around permission gates, snapshots, audit records, and rollback paths.
- Keep provider integrations fail-visible and replaceable.
- Model marketplace workflows as state machines before payment or public listing logic.

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

### Commerce Platform Modernization

https://github.com/shiny-a2/commerce-platform-modernization-showcase

Architecture planning, data modeling, migration strategy, RBAC boundaries, SEO control-plane thinking, and modular commerce platform design.

### WooCommerce Performance Lab

https://github.com/shiny-a2/a2-woocommerce-performance-lab

Microcache boundaries, REST route control, Action Scheduler cleanup, transient protection, autoload hygiene, and low-overhead diagnostics for WooCommerce stores under real traffic pressure.

### CRM Operations System

https://github.com/shiny-a2/a2-crm-operations-system

WordPress-based CRM architecture for operator inboxes, customer follow-up, customer hubs, SMS/VoIP integration boundaries, reporting, and operational auditability.

### Commerce Automation Workflows

https://github.com/shiny-a2/commerce-automation-workflows-showcase

n8n-style workflow architecture for CRM routing, reporting pipelines, messaging review gates, Google Sheets handoffs, and approval-safe operational automation.

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

### Automation Workflows

- [Commerce automation architecture notes](https://github.com/shiny-a2/commerce-automation-workflows-showcase/blob/main/docs/architecture-notes.md)

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
