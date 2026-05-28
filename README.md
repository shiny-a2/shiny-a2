# Amirali Yaghouti

Senior WordPress / WooCommerce Performance & Infrastructure Engineer

I work on production commerce systems where slow pages, heavy WooCommerce routes, database pressure, checkout noise, and operational friction need to become measurable engineering problems.

My strongest work is around WooCommerce performance engineering, MU-plugin architecture, high-traffic WordPress systems, custom operational tooling, product/API integrations, CRM/customer operations, Action Scheduler and database optimization, and Elementor-heavy production websites.

Portfolio: https://amiraliyaghouti.com  
LinkedIn: https://www.linkedin.com/in/amirali-yaghouti  
GitHub: https://github.com/shiny-a2

## Selected Impact

- Product detail page TTFB: 2.3s -> 0.9s
- Product archive p95: 5.2s -> 1.7s
- REST route p95: 2.8s -> 0.9s
- Product API p95: 1.9s -> 0.42s
- Action Scheduler pending queue: about 38k -> about 4.9k
- Transient rows: about 1.3M -> about 180k
- Similar-products block render: 1.9s -> 0.42s

## Technical Focus

- WordPress, WooCommerce, PHP, MySQL, JavaScript
- MU-plugins, custom plugins, hooks, admin UX, checkout/cart flow
- LiteSpeed, full-page microcache, transient control, autoload optimization
- REST APIs, snapshot tables, rate limits, allowlists, rebuild jobs
- Action Scheduler, WP-Cron, diagnostics, performance logging
- CRM systems, operator workflows, customer hubs, SMS/VoIP integrations
- n8n, reporting workflows, Google Sheets/API automation

## Featured Case Studies

### WooCommerce Performance Engineering

[`a2-woocommerce-performance-lab`](https://github.com/shiny-a2/a2-woocommerce-performance-lab)  
Microcache, REST route control, Action Scheduler tuning, transient cleanup, autoload guards, and production-safe performance logging for WooCommerce stores.

### WooCommerce API & Product Data

[`a2-searchwiz-product-api`](https://github.com/shiny-a2/a2-searchwiz-product-api)  
Snapshot-based product API architecture that moves heavy product reads away from live WooCommerce queries.

### CRM / Customer Operations

[`a2-crm-operations-system`](https://github.com/shiny-a2/a2-crm-operations-system)  
WordPress-based CRM architecture for operator inboxes, customer tracking, sales follow-up, reporting, and provider integrations.

### Recommendation Systems

[`a2-style-dna-similar-products`](https://github.com/shiny-a2/a2-style-dna-similar-products)  
Product similarity architecture using signatures, cached candidate scoring, and anti-stampede protection.

### Admin Operations Tooling

[`a2-woocommerce-admin-ops-toolkit`](https://github.com/shiny-a2/a2-woocommerce-admin-ops-toolkit)  
Order operation tools, admin modal workflows, operational flags, and safer WooCommerce productivity tooling.

### Marketplace Architecture

[`a2-watch-marketplace-showcase`](https://github.com/shiny-a2/a2-watch-marketplace-showcase)  
Architecture and implementation showcase for watch marketplace workflows. Production launch is not represented.

## Public Code Policy

Public repositories contain curated, anonymized samples and architecture documentation. Production secrets, customer data, private business logic, server paths, internal URLs, and sensitive operational details are intentionally excluded.

