# Northstar School OS website — Release 0.1.0

**Date:** 27 October 2026  
**Type:** First complete marketing website preview

## Included

- Responsive, multi-page marketing experience with shared top navigation and footer.
- Product positioning from preschool / early-years education through Grade 12 and multi-campus schools.
- Home page with illustrative operations dashboard, stage explorer, role-specific walkthrough, school workflow narrative and FAQs.
- Platform page covering existing modules, school-data boundaries and product rollout readiness.
- School segment page, philosophy page, contact preview and privacy notice.
- Interactive mobile navigation, grade explorer, role explorer and FAQ accordions.
- Contact-form validation, opt-in backend hook and honest no-transmission fallback.

## Checks performed

- Validated all internal relative page links and hash targets.
- Checked all 6 pages contain meaningful page content, exactly one primary heading and meta description.
- Checked for duplicate element IDs.
- Passed JavaScript syntax check (`node --check`).
- Parsed CSS successfully with no top-level parser errors.

## Known release blockers before going live

1. No verified domain or hosting deployment has been configured.
2. No verified email address / secure contact-form endpoint has been provided; submissions are not sent in preview mode.
3. Browser-based rendered visual regression tests could not run in the creation environment because Chromium navigation was blocked by an administrator policy. Device breakpoints were designed but visual review in an actual browser remains a launch check.
4. The site must undergo product-owner approval, secure live-form tests and final accessibility/privacy review before public promotion.

## Product messaging note

Core features are aligned with the existing Northstar School OS project README; incomplete pilot integrations are explicitly acknowledged. No customer claims, live usage figures or certifications have been invented.

## 2026-10-27 — Walkthrough enquiry integration
- Added native FormSubmit email form integration with explicit receiving-inbox selection at publish time.
- Added consent and honeypot inputs, third-party processor privacy notice, and success page.
- Removed non-transmitting preview-mode JavaScript.
- FormSubmit inbox activation and a confirmed received test are mandatory before relying on lead email delivery.

## 2026-10-27 — Google Sheets lead backend package

- Prepared Apps Script receiver to replace FormSubmit and its activation dependency.
- Writes valid requests to the shared `Enquiries` sheet; includes consent, simple spam trap, input validation and formula-injection protection.
- Sends a notification to `enquire@northstarschoolos.com`; saves the lead even if email sending fails.
- Switched the enquiry form's HTML POST destination to a deployment placeholder filled by the new safe deploy script.
- Updated website privacy text for Google Apps Script/Sheets rather than FormSubmit.
- Pending user action: authorise and deploy Apps Script, deploy website HTML, and verify live submissions. The website is not yet using this backend merely because the package was prepared.
