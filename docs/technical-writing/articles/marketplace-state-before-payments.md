# Model Marketplace State Before Payment Implementation

Marketplace projects can become payment projects too early. Payment is important, but for high-value items it is not the first hard problem.

The first hard problem is state and trust.

Before a marketplace decides how money moves, it needs to decide what an item is allowed to be, who has reviewed it, whether it can be listed, whether it is reserved, who holds it, and what conditions must be true before settlement is even considered.

## Problem Context

A simple product catalog can often treat items as draft, published, sold, or archived. A marketplace for high-value goods has more responsibility. Seller submission, operator review, authenticity checks, listing approval, reservation, custody, delivery, return, and settlement are separate concerns.

If those concerns collapse into one status, the system becomes hard to reason about. A listing might look approved while custody is unresolved. A payment path might proceed before review is complete. A seller submission might become public before an operator has checked it.

Those are state problems before they are UI or payment problems.

They are also support problems. When a status is ambiguous, staff have to reconstruct history manually. That slows down exceptions and makes it harder to explain what happened to a buyer, seller, or internal reviewer.

Good state design gives the team a shared vocabulary before money, custody, and public listing behavior make mistakes more expensive.

## Why It Matters

Trust-heavy marketplaces depend on valid transitions. A buyer should not be able to reserve an item that was never approved for listing. Settlement should not move forward because one generic status says approved while authenticity or custody remains unclear.

The system needs to make invalid movement difficult.

That does not require exposing private verification rules publicly. In fact, public documentation should avoid sensitive verification methods. But the architecture can still show the boundary: authenticity state is not the same as custody state, and neither is the same as settlement readiness.

## Practical Architecture

I would start with a state map before implementing payment behavior.

At minimum, the system needs states for submission, review, approval, rejection or needs information, listing, reservation, custody, delivery, return, and settlement readiness. The exact names can change, but the responsibilities should not be blurred.

Transitions should be explicit. A submitted item can move to under review. An under-review item can be approved, rejected, or marked as needing information. An approved item can become listed. A listed item can be reserved. A reserved item may enter custody workflows. Settlement readiness should depend on multiple conditions, not one generic approval flag.

Operator actions should be auditable. If a state changes, the system should know who changed it and why. That audit trail does not need to reveal sensitive verification details in public samples. It does need to exist in the real system.

## Tradeoffs

State-machine work can feel slow before the marketplace UI looks complete. It may not produce the same visible progress as checkout screens or listing pages.

But the cost of skipping it appears later. Ambiguous state makes exceptions harder, customer support harder, reporting harder, and payment behavior riskier.

There is also a communication tradeoff. Product teams may want fewer states because fewer states look simpler. Engineering may need more states because the process has real boundaries. The useful compromise is not to add states for decoration. Add states where responsibility changes.

## Failure Modes

One failure is attaching payment behavior to an item that was never validly reviewed or publishable.

Another is merging custody and authenticity into one approval concept. An item can be authentic but not in the right custody state. It can be in custody while settlement is still blocked. Those distinctions matter.

A third failure is leaving exception paths undocumented. Returns, rejected submissions, missing information, expired reservations, and operator overrides need boundaries before they happen under pressure.

## What I Would Monitor

I would monitor invalid transition attempts, state age, items stuck in review, reservation expiry, custody state changes, settlement-blocking conditions, operator overrides, and audit events for high-risk transitions.

For public documentation, I would show the state categories and dependency boundaries without revealing verification methods, dispute procedures, or sensitive operational rules.

Related public repo: https://github.com/shiny-a2/a2-watch-marketplace-showcase

Related portfolio link: https://amiraliyaghouti.com/case-studies.html
