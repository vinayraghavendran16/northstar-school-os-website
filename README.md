# Northstar School OS — Marketing site

A responsive, multi-page marketing site hosted as static pages on GitHub Pages. This repository is **separate** from the Northstar school application (`neverskipalternate`).

## Enquiry capture

The contact form posts normally (without JavaScript fetch) to a Google Apps Script web app:

1. Apps Script writes the submitted enquiry into the existing private Google Sheet `Northstar School OS — Website Enquiries` → `Enquiries`.
2. Apps Script then sends a notification email to `enquire@northstarschoolos.com`.
3. If email sending fails, the lead is still saved and Status becomes `Email failed`.
4. The visitor sees a confirmation or error page hosted by Google Apps Script.

**Important:** This code must be deployed and authorised from your Google account. The link is not live until you deploy Apps Script and publish the static form that points to its web app URL. A rendered thank-you page alone is not proof of delivery; verify a real Sheet row and mailbox delivery.

See [DEPLOYMENT.md](DEPLOYMENT.md) for precise setup steps and troubleshooting. Paste `Code.gs` into **Extensions → Apps Script** in the Sheet, and run `bash deploy-to-github-pages.sh` from the website folder after copying the Apps Script `/exec` URL. The script only touches the dedicated Northstar marketing website repository.

## Contents

- `index.html`: homepage with interactive stages, school roles and FAQs
- `platform.html`: modules and product overview
- `schools.html`: audiences and use cases
- `approach.html`: product principles
- `contact.html`: enquiry form (requires deployment URL)
- `privacy.html`: website privacy notice
- `thanks.html`: legacy static confirmation page (not used by Apps Script)
- `Code.gs`: server-side Apps Script receiver, Sheet write and MailApp alert
- `deploy-to-github-pages.sh`: safe GitHub Pages publishing script

## Privacy and limitations

The public endpoint accepts unauthenticated submissions and uses a honeypot, not a full CAPTCHA; it can be spammed. Do not collect student, medical or other sensitive records through this form. The Sheet must stay private. Email alerts depend on Google account authorisation and Apps Script mail quotas. Do not misrepresent the integration as verified until end-to-end tested.
