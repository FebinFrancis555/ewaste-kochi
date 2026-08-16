# EWaste Kochi

Astro-based programmatic SEO website for e-waste recycling, electronics recovery, IT asset disposition, and related services in Kerala.

## Clean-build scope

This repository is a **source build**, not a production audit archive. It intentionally contains no GSC exports, deployment IDs, crawl reports, remediation logs, historical production evidence, or certification evidence.

Claims about authorizations, certifications, ratings, offices, fleet size, service guarantees, or other regulated/business facts must be backed by first-party evidence before being published.

## Information architecture

The core programmatic model is:

- **30 location pillars**
- **17 service pillars**
- **510 location × service pages** (`30 × 17`)
- **12 core routes**
- **569 nominal pages** when all declared routes build successfully (`30 + 17 + 510 + 12`)

The exact built URL count is a build artifact and must be verified from the generated output rather than treated as a production fact.

## Source of truth

- `src/data/locations.js` — location dataset
- `src/data/services.js` — service dataset
- `src/data/faqs.js` — FAQ content
- `src/data/blogs.js` — blog metadata/content inputs
- `src/pages/locations/[location].astro` — location pillar route
- `src/pages/locations/[location]/[service].astro` — location/service matrix route
- `src/pages/services/[service].astro` — service pillar route
- `src/layouts/BaseLayout.astro` — shared document head, structured data, and layout shell
- `public/robots.txt` — canonical crawler policy for the source site

## Build

```bash
npm install
npm run build
npm run preview
```

Astro's static build is the only build target in this repository. The sitemap integration emits the sitemap from the routes that actually build; there is no hand-maintained production URL inventory in this repository.

## SEO principles

1. One canonical URL per intended route.
2. Every indexable page must be reachable through the site's information architecture or be explicitly documented as intentionally non-indexable.
3. Programmatic pages must provide meaningful location/service-specific information rather than token-swapped doorway content.
4. Structured data must describe facts that can be substantiated.
5. Sitemap membership follows successful route generation; it is not a substitute for internal linking.
6. No historical production state is used as a source of truth for the clean build.

## Content and compliance language

Use precise language such as **"designed for compliance-aware workflows"** unless a specific authorization, certification, or accreditation is documented and approved for publication. Do not infer KSPCB authorization, NIST certification, government approval, ratings, or third-party partnerships from generic standards references.

## Repository hygiene

Deployment-specific configuration, redirect inventories, domain verification files, audit reports, crawl exports, temporary remediation artifacts, and machine-generated production evidence do not belong in this source repository.
