# Northstar School OS — Marketing website

A responsive, multi-page static marketing website for Northstar School OS.

## Run locally

From this folder: `python3 -m http.server 8000` and open `http://localhost:8000`. Or open `index.html` directly in a browser. No build step needed.

## Pages

- `index.html`: home, interactive stage & role explorers, FAQ
- `platform.html`: school OS modules, permissions, readiness
- `schools.html`: school segments, outcomes, onboarding
- `approach.html`: positioning and design principles
- `contact.html`: school walkthrough enquiry form using FormSubmit (activation required)
- `thanks.html`: thank-you page after form submission
- `privacy.html`: preview privacy information

## Before publishing as a production site

1. **Activate FormSubmit email delivery.** Submit a test enquiry from the live site, then open the confirmation email sent by FormSubmit to your chosen receiving inbox and activate the form. Verify that a second test enquiry arrives. Until activated and verified, email delivery is **not confirmed**. Choose a business inbox when running the deployment script and activate that recipient.
2. Add verified support/contact details and comprehensive privacy/terms as needed.
3. Confirm messaging, legal claims, accessibility and actual product capabilities with the live Northstar team.
4. Set canonical URL, Open Graph metadata and a website domain.
5. Validate hosting, CSP and analytics/consent before go-live.

## Product-alignment notes

Based on the existing Northstar School OS application repository `vinayraghavendran16/neverskipalternate` README at the time of creation. No fabricated testimonials, partner logos, deployment counts, security certifications or pricing. Dashboard figures are labeled **illustrative**.

The form is integrated with a third-party form processor. It requires email activation and end-to-end verification; never use it for student or sensitive data. The deploy script asks you for the receiving email; it will be written into the public form action. Prefer a business inbox.

## Deploy on GitHub Pages

See [DEPLOYMENT.md](DEPLOYMENT.md) or run `bash deploy-to-github-pages.sh` from this directory after authenticating Git with GitHub. This publishes the website to the dedicated `vinayraghavendran16/northstar-school-os-website` repository on its `main` branch. It does not touch `neverskipalternate` or its application code.

## Form delivery integration (2026-10-27)

On the live `contact.html` page, the form POSTs to FormSubmit for email delivery, with required fields for contact identity, school stage and consent. A hidden bot-trap field is included and FormSubmit may display anti-spam verification. `thanks.html` is the configured success redirect. **Activation is required.** Test with non-sensitive dummy contact data before advertising the form.

**Receiving inbox:** The published form `action` receives your address from the deployment script prompt (or `NORTHSTAR_CONTACT_EMAIL` environment variable). Choose an email you control. To switch, run the deployment script again with the new address and complete FormSubmit activation.
