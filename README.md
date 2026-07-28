# Obsidianweb — Prototype

Private search engine prototype

Privacy today, privacy tomorrow, privacy forever.

This repository contains a minimal prototype of Obsidianweb: a pitch-black UI and a backend sketch demonstrating the binary-matching search flow you described:

- Convert query to binary
- Fetch a set of configured seed sites
- Convert site text to binary
- Compute similarity between query-binary and site-binary and return matching snippets

Important safety notes

- This prototype is for demonstration and development only. It does not provide a production VPN, relay, or hardened browser.
- By default the server includes a simple moderation check. Disabling moderation is allowed only when an ADMIN_TOKEN environment variable is provided and used via the moderation query parameter. This is to avoid accidental enabling of an unsafe configuration in shared environments.
- Do not use this prototype to facilitate illegal activity. If you plan to deploy this publicly, implement robust moderation, rate-limiting, user warnings, legal terms, and secure VPN/relay infrastructure.

Getting started

1. Clone the repo and install dependencies:

   npm install

2. Run the server:

   npm start

3. Open the prototype UI in a browser:

   http://localhost:3000

Files added

- README.md — this file
- package.json — Node project file
- server/index.js — Express server implementing /api/search
- public/index.html — frontend prototype
- .gitignore

Configuration

- PORT — server port (default 3000)
- ADMIN_TOKEN — optional. When set, calls to /api/search can disable moderation by adding `&moderation=off&admin_token=<ADMIN_TOKEN>`.
- SEED_SOURCES — not implemented via env in this simple prototype; modify server/index.js to change the seeded sites.

Next steps

- Replace the seed sources with a curated crawl or search aggregator
- Implement proper rate limiting, caching, and request parallelism
- Add real VPN/relay infrastructure and do a privacy/security audit
- Hook ObsidianAI to a safe LLM endpoint with configurable moderation and logging
