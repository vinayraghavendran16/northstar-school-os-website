# Northstar School OS — Marketing website

A responsive, multi-page static marketing website for Northstar School OS.

## Run locally

From this folder: `python3 -m http.server 8000` and open `http://localhost:8000`. Or open `index.html` directly in a browser. No build step needed.

## Pages

- `index.html`: home, interactive stage & role explorers, FAQ
- `platform.html`: school OS modules, permissions, readiness
- `schools.html`: school segments, outcomes, onboarding
- `approach.html`: positioning and design principles
- `contact.html`: accessible lead enquiry preview
- `privacy.html`: preview privacy information

## Before publishing as a production site

1. Configure an approved secure form destination in `assets/site.js` (`CONTACT_ENDPOINT`), then test delivery and error handling. Until set, the enquiry form **does not transmit data**; it offers a local copy/email draft.
2. Add verified support/contact details and comprehensive privacy/terms as needed.
3. Confirm messaging, legal claims, accessibility and actual product capabilities with the live Northstar team.
4. Set canonical URL, Open Graph metadata and a website domain.
5. Validate hosting, CSP and analytics/consent before go-live.

## Product-alignment notes

Based on the existing Northstar School OS application repository `vinayraghavendran16/neverskipalternate` README at the time of creation. No fabricated testimonials, partner logos, deployment counts, security certifications or pricing. Dashboard figures are labeled **illustrative**.

The form demo intentionally does not claim backend connectivity. There is no deployment bundled with this download.

## Deploy on GitHub Pages

See [DEPLOYMENT.md](DEPLOYMENT.md) or run `bash deploy-to-github-pages.sh` from this directory after authenticating Git with GitHub. This publishes the website to the dedicated `vinayraghavendran16/northstar-school-os-website` repository on its `main` branch. It does not touch `neverskipalternate` or its application code.
