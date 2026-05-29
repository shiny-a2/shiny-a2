# Similar Products Without Expensive Real-Time Catalog Scans

A similar-products block can look like a small UI feature. On a WooCommerce product page, it is more than that. It is a data-selection problem sitting on one of the most important routes in the store.

If the block scans the catalog during every product detail page render, the feature can quietly turn product discovery into a performance problem.

The safer question is: what work can be moved out of the render path?

## Problem Context

Product pages are high-intent pages. They already have enough work to do: product data, images, price logic, stock context, variations, plugin hooks, SEO output, structured data, and theme rendering. Adding recommendation logic directly into that request can make the page slower and less predictable.

Recommendation logic is often heavier than it looks. It may compare attributes, categories, tags, price bands, styles, inventory state, availability, or business rules. Even when each check is small, the work grows with catalog size.

That is why I prefer signatures and cached candidate snapshots over live scans.

The problem is not only database time. It is predictability. A product page that is fast for one item and slow for another because candidate scoring behaves differently is harder to tune and harder to explain.

## Why It Matters

A recommendation block should help discovery without making the buying page worse. If it adds a slow query path to every product view, the store pays for that feature on every high-intent request.

The risk is not always obvious in development. A local catalog or small test dataset may behave fine. Production catalogs, imports, attribute changes, cache churn, and plugin hooks can expose the real cost later.

Performance work here is not about removing recommendations. It is about choosing where the expensive work belongs.

## Practical Architecture

The first step is to represent each product as a compact signature. The signature can include public-safe attributes such as product type, category group, visible terms, price band, availability class, or other business-approved signals. Private merchandising weights should stay private.

Then candidate selection can happen outside the normal render path where possible. The system can build or refresh candidate snapshots when a product changes, when a scheduled rebuild runs, or when a controlled maintenance process executes.

The product page should render from cached IDs. At request time, the block should do as little as possible: load the candidate list, verify basic visibility, apply a render budget, and return a fallback if data is missing.

Cache keys should include the source product signature or fingerprint. If the source product changes, its recommendations may need a rebuild. If a candidate changes, it may affect more than one source product. That does not mean every catalog edit should rebuild everything. It means invalidation should be planned.

## Tradeoffs

Cached recommendations can be slightly stale. Live recommendations may be more current. On a production product page, predictable render cost often matters more than perfect freshness.

Another tradeoff is complexity. Signatures, fingerprints, rebuild locks, and candidate snapshots require more design than a direct query. The benefit is that the system becomes easier to reason about under traffic.

There is also a product tradeoff. A fallback recommendation list may be less precise than a freshly scored list. But a fast fallback is better than a recommendation block that slows the whole page or fails noisily.

## Failure Modes

One failure is a recommendation widget that works well in testing and becomes a hidden slow path in production.

Another failure is global invalidation. If every product import clears every recommendation cache, the next wave of traffic may trigger expensive rebuilds at the worst time.

A third failure is no invalidation at all. The block stays fast, but recommendations become stale enough that staff stop trusting it.

The goal is a middle path: scoped invalidation, rebuild locks, render budgets, and fallback behavior.

## What I Would Monitor

I would monitor product page render time with and without the recommendation block, candidate cache hit rate, rebuild duration, rebuild queue size, stale snapshot age, fallback frequency, and duplicate rebuild attempts.

I would also monitor catalog changes that affect many fingerprints at once. Imports and bulk edits are often where recommendation systems show whether their invalidation design is calm or fragile.

Related public repo: https://github.com/shiny-a2/a2-style-dna-similar-products

Related portfolio link: https://amiraliyaghouti.com/case-studies.html
