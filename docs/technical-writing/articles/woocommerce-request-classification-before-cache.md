# Why WooCommerce Performance Starts With Request Classification

WooCommerce performance work often starts with a familiar request: "make the store faster." The first instinct is usually cache. Cache can help, but on a commerce site it can also make a system faster and less correct at the same time.

The first question is not "what can we cache?" The first question is "what kind of request is this?"

That distinction matters because a WooCommerce site is not one surface. A product detail page, product archive, cart, checkout, account page, order payment route, payment callback, admin AJAX request, REST route, and Elementor preview can all pass through the same WordPress installation with very different safety rules. Treating every `GET` request as public is how a speed fix turns into a checkout or customer-state problem.

## Problem Context

Product pages and archives are usually good performance candidates. They often receive repeated anonymous traffic, and much of the output changes slowly enough to benefit from short-lived cache or precomputed fragments.

Cart and checkout are different. Account pages are different. Requests with WooCommerce session cookies are different. Logged-in requests are different. Payment and order routes are different again. Even when a route looks public, it may carry state that changes what should be rendered.

This is why I prefer to put a request classifier in front of cache decisions. It is a small boundary, but it changes the shape of the work. Instead of asking cache logic to understand everything, the system first decides whether the request is safe to optimize at all.

## Why It Matters

The worst failure in WooCommerce performance is not a cache miss. A cache miss is slower than ideal, but usually correct. The worse failure is serving the wrong commerce state: stale cart fragments, customer-sensitive output, checkout-sensitive content, or a response that ignores session context.

That kind of bug is hard to explain to a customer and hard for staff to trust afterward.

Performance work on a live commerce system has to respect that some slow paths are slow because they are protecting correctness. The goal is not to bypass that protection. The goal is to identify where the protection is needed and where it is not.

## Practical Architecture

A useful request classifier does not need to be dramatic. It needs a clear order of decisions.

Start with method and route. Unsafe methods and write paths should exit early. Then check authenticated and privileged requests. Then check known WooCommerce surfaces: cart, checkout, account, order-pay, payment callbacks, admin, AJAX, and preview routes.

Cookies matter. If a request has cart or session cookies, I would rather bypass public-page cache than guess. That is conservative, but it keeps the store honest.

Only after those checks should a product page, archive, search page, or other public route enter an optimization path. Even there, cache eligibility should be explicit. Some routes are public but still not good cache candidates because they depend on query combinations, personalization, stock context, or unstable plugin output.

Diagnostics should record the request class, not customer details. A useful log line is "guest product page, cache eligible, miss, render time high." It does not need names, emails, order IDs, or private payloads.

## Tradeoffs

Conservative classification leaves some performance on the table. A request with a harmless-looking cookie might bypass cache even though the output would have been safe. That is acceptable in many production stores. A missed cache hit is cheaper than leaking or corrupting commerce state.

The other tradeoff is maintenance. Every store has its own plugin stack. A classifier has to be reviewed when new checkout extensions, membership systems, language switchers, or pricing rules are added. That review is not overhead; it is part of operating a store safely.

## Failure Modes

The obvious failure is classifying too broadly and caching sensitive output. The quieter failure is classifying too narrowly and never getting meaningful performance gains.

Another common failure is treating REST/API pressure as the same problem as page-render pressure. Anonymous REST reads can create backend load even when the page cache looks healthy. I usually separate route pressure from page cache decisions because the mitigation is different.

Finally, a classifier can become a pile of special cases if nobody owns it. The best version is boring: clear bypass rules, clear eligible routes, and a small fixture or checklist for reviewing new cases.

## What I Would Monitor

I would monitor cache hit/miss by request class, slow requests by route, bypass reasons, REST route pressure, and whether unsafe paths ever enter cache-eligible logic. I would also track external HTTP delays on frontend paths, because a slow provider should not hold a product page open.

The monitoring should help answer: "What did we decide this request was?" Without that answer, performance data is just timing without context.

Related public repo: https://github.com/shiny-a2/a2-woocommerce-performance-lab

Related portfolio link: https://amiraliyaghouti.com/case-studies.html

