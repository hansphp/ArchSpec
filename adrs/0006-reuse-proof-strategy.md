# ADR 0006: Reuse Proof Strategy

## Status

Accepted

## Context

ArchSpec is intended to be a reusable framework rather than a disguised single-product repository.

However, reuse has not yet been proven operationally.

The framework therefore needed an explicit decision about what counts as acceptable proof of reuse in the near term.

The risk of not deciding this is that:

- generator work expands before reuse is demonstrated,
- the active product silently becomes the framework's hidden center,
- and architecture choices absorb business assumptions that belong only to one product.

## Decision

The first proof of reuse for ArchSpec will be:

- a second product under `products/`,
- using the same architecture manifest,
- validated by the same schema and validator strategy,
- with an explicit comparison of capability reuse across both products.

This reuse milestone should be completed before ArchSpec broadens generator complexity significantly.

The first proof of reuse does not yet require:

- a second architecture profile,
- full portability across multiple stacks,
- or a large catalog of products.

Those are later proof layers, not the first one.

## Consequences

### Positive

- The framework will be tested against more than one business domain early enough to expose hidden coupling.
- Capability contracts will be pressured by real variation instead of one example only.
- Product-specific assumptions are more likely to surface before the generator surface becomes large.

### Costs

- A second product must be curated before some later framework ambitions.
- The team must resist the temptation to optimize only for the current active product.

## Immediate implications

The next reuse milestone should require:

1. a second product spec under `products/`,
2. validation of both products with the same schema strategy,
3. reuse comparison notes for requested capabilities,
4. confirmation that the architecture manifest remains domain-agnostic across both products.

## Non-goals

This decision does not imply:

- proving multi-stack portability before single-stack reuse exists,
- adding many products before one second product proves the point,
- or treating generator sophistication as a substitute for reuse proof.
