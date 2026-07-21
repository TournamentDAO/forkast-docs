# Forkast Documentation

Source for the Forkast documentation site, published with [Jamdesk](https://jamdesk.com).

[Forkast](https://forkast.gg) is a prediction-market trading platform. This repo contains:

```
forkast-docs/
├── docs.json              # Site configuration (theme, colors, navigation)
├── knowledge-center/      # User-facing guides: platform mechanics, rewards, FAQs, policies
├── developers/            # Developer docs: SDK integration guide, websockets, MCP server
├── api-reference/         # REST API endpoint pages (generated from the OpenAPI spec)
└── openapi/
    └── forkast-api.yaml   # Forkast REST API OpenAPI 3.0 specification
```

## How publishing works

Jamdesk is connected to this repository. **Every push to the default branch triggers a build and deploys the site automatically** — no CI/CD setup required.

## Editing content

Pages are MDX (Markdown + components). The file path becomes the page URL, and sidebar structure is defined in `docs.json` under `navigation`.

Preview locally with the Jamdesk CLI:

```bash
npm install -g jamdesk
jamdesk dev          # http://localhost:3000
jamdesk validate     # check for errors
jamdesk broken-links # check for broken links
```

### API reference pages

Endpoint pages under `api-reference/` are thin MDX stubs bound to the OpenAPI spec via frontmatter, e.g.:

```mdx
---
title: "Get user profile"
openapi: "/openapi/forkast-api.yaml GET /user/profile"
---
```

To change request/response documentation, edit `openapi/forkast-api.yaml` — the endpoint pages render from it.

## Content source

The content was migrated from the Archbee workspace export (Forkast Knowledge Center + Forkast Developer Docs spaces) on 2026-07-21.
