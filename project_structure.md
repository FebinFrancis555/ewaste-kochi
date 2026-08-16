# EWaste Kochi — source architecture

```text
src/
├── components/       shared navigation, footer, widgets
├── data/             locations, services, FAQs, blog inputs, contact data
├── layouts/          shared HTML/SEO/schema shell
└── pages/
    ├── core routes
    ├── blog/
    ├── industries/
    ├── locations/
    │   ├── [location].astro
    │   └── [location]/[service].astro
    └── services/
        └── [service].astro
public/
└── static assets and crawler policy

astro.config.mjs
package.json
README.md
```

## Programmatic model

`locations.js` supplies the location dataset and `services.js` supplies the service dataset. The matrix route creates one page for every valid location/service pair.

Nominal core model:

- 30 location pillars
- 17 service pillars
- 510 location/service matrix pages
- 12 core routes
- 569 pages before any additional blog or utility routes are counted

The source repository does not contain a hand-written production URL inventory. The generated sitemap is derived from routes that successfully build.

## Clean-build boundary

This repository intentionally excludes deployment-specific redirect maps, verification files, production audit reports, GSC exports, deployment identifiers, and historical remediation artifacts.
