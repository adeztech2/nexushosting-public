# ADEZ NEXUS HOSTING redesign plan

## Implementation approach

Keep the existing Express server, API routes, authentication, database helpers, deployment engine, GitHub OAuth, Paystack flow, SSE logs, admin controls, and worker configuration unchanged. Redesign the existing single-page frontend in `public/index.html` in place by replacing the visual system, shared layout helpers, landing page composition, branding, cards, inputs, buttons, and responsive behavior while retaining the current hash router and all API calls.

Add the selected transparent logo asset at `public/adez-nexus-hosting-logo.png`, use it in the favicon, navigation, authentication, loading, dashboard, and landing surfaces, and use ADEZ TECH as the parent-brand eyebrow. Technical identifiers such as existing API paths, storage domains, database names, and worker resource names remain unchanged so existing deployments and integrations are not disrupted.

## Project structure

- `public/index.html`: single-page frontend, hash routing, views, and API client.
- `server.js`: Express HTTP server, authentication, GitHub OAuth, billing, admin APIs, static serving, and email messages.
- `db.js`: MongoDB/local JSON persistence layer.
- `engine.js`: project detection, deployment engine, logs, storage, and runtime helpers.
- `runner.js`: deployment/runtime support code retained as supplied.
- `worker/`: Cloudflare Worker/R2 configuration retained as supplied.

## Design direction

### Candidate styles

- **Terminal Luxe** (0.06): dark operator console with vivid green telemetry and command-line cues.
- **Emerald Infrastructure** (0.58): premium dark SaaS with luminous green infrastructure motifs, glass cards, and confident editorial spacing.
- **Carbon Grid** (0.04): strict monochrome technical grid with restrained green highlights.

### Chosen style: Emerald Infrastructure

**Design Movement:** premium dark developer SaaS influenced by Vercel, Linear, and modern infrastructure control planes, but with a distinctly emerald ADEZ TECH signature.

**Core Principles:** infrastructure-first clarity; luminous green hierarchy; generous editorial spacing; dense information only where an operator needs it.

**Color Philosophy:** `#050505` gives the platform a high-trust command-center base; `#171717` and the `#0D1915 → #171D1A` card gradient create depth; `#6EE7B7` and `#10B981` signal healthy systems and action; `#9CA3AF` keeps supporting information calm; `#262626` keeps boundaries precise without visual noise.

**Layout Paradigm:** asymmetrical editorial landing page with a left-aligned headline, a floating deployment telemetry panel, and modular cards; authenticated views use a wide operator canvas with clear content rails instead of generic centered forms.

**Signature Elements:** emerald telemetry dots; soft radial infrastructure glows; dark glass cards with hairline borders; the three-node ADEZ Nexus mark.

**Interaction Philosophy:** actions should feel immediate and operational; primary actions glow subtly on hover, cards lift by a few pixels, status indicators pulse only for live/queued work, and destructive actions remain visually separated.

**Animation:** 160–220ms ease-out transitions, gentle entrance fade/slide, no distracting loops except live status indicators and ambient hero glow.

**Typography System:** system UI stack for reliability and fast rendering; bold condensed-feeling display hierarchy through tight tracking and large line-height contrast; monospace only for URLs, commands, environment variables, and logs.

**Brand Essence:** ADEZ NEXUS HOSTING is the reliable launchpad for Kenyan builders and teams who want to ship from GitHub without managing servers. Personality: precise, optimistic, capable.

**Brand Voice:** confident and operational, never inflated. Example lines: “Ship without the server room.” and “Your next deployment deserves a cleaner runway.”

**Wordmark & Logo:** use the supplied three-node Nexus mark as the scalable symbol; pair it with the exact ADEZ NEXUS HOSTING wordmark and a small ADEZ TECH parent-brand eyebrow.

**Signature Brand Color:** electric emerald `#10B981`, softened by mint `#6EE7B7` for highlights.
