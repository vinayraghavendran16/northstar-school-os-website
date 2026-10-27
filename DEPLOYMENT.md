# Northstar School OS — Connect website enquiries to Google Sheets

The **Northstar website is already live**. You do **not** need a new repository or to change GitHub Pages settings. This is a one-time replacement of the unreliable FormSubmit backend.

## What is already set up

- Tracker: [Northstar School OS — Website Enquiries](https://docs.google.com/spreadsheets/d/1JgGCUQSxoYcAkfznBEs-A2RxjjsfllXYtfNxfyWtQRA/edit)
- Sheet tab: `Enquiries`
- Notification inbox: `enquire@northstarschoolos.com`
- Website: `https://vinayraghavendran16.github.io/northstar-school-os-website/`

## 1. Authorise the Google Apps Script backend (in your Google account)

1. Open the tracker above. Use your personal Google account with **Editor** access (`vinayraghavendran16@gmail.com`).
2. Select **Extensions → Apps Script**.
3. Delete the placeholder `myFunction()` from `Code.gs`, then copy **all** the text from the provided `Code.gs` into it.
4. Click **Save**. Name the project `Northstar School OS — Lead Receiver`.
5. Choose **Deploy → New deployment**. Click the gear/select type icon and choose **Web app**.
6. Set **Execute as → Me**; **Who has access → Anyone**. **Anyone** is required for school owners who are not signed into Google. The spreadsheet remains private; only the POST endpoint is public.
7. Click **Deploy**, authorise access to Google Sheets and email, and copy the **Web app URL** ending `/exec`. If your Workspace organization does not permit *Anyone* access, use a personal Gmail editor account or an approved backend instead.
8. Paste that URL into a browser and verify it says **“Northstar form receiver is ready”**. This only verifies deployment, not successful form submission.

## 2. Publish the website change

On your Mac, download the accompanying website ZIP, which contains the `northstar-school-os-website` folder. In Terminal:

```bash
cd ~/Downloads
unzip -o Northstar-School-OS-Google-Sheets-Integration.zip
cd ~/Downloads/northstar-school-os-website
bash deploy-to-github-pages.sh
```

The script is already configured with your deployed Apps Script URL. You do **not** need to paste it again. The script clones and publishes to **only** the existing public `vinayraghavendran16/northstar-school-os-website` GitHub repo. The app repository is untouched.

**Do not re-run the older deployment ZIP**: it still targets FormSubmit. Keep this version for future deployments.

## 3. Test the end-to-end flow

1. Open the live [walkthrough request](https://vinayraghavendran16.github.io/northstar-school-os-website/contact.html) after its GitHub Pages deployment has completed.
2. Inspect the form's HTML action by using browser View Source; it should be your `https://script.google.com/macros/s/.../exec` URL, **not** FormSubmit.
3. Submit a test with a fictional school. You will be taken to a branded Google Apps Script **Your request has been recorded** page with a link back to Northstar.
4. Confirm a new row is present in the `Enquiries` Google Sheet.
5. Confirm an email arrives at `enquire@northstarschoolos.com` with the test enquiry details. The message is sent **from the Google account that deployed the script**, not from the Northstar inbox.
6. If a row exists but email does not arrive, check the row's **Status** column; `Email failed` indicates Apps Script logged an email-sending error. Open Apps Script **Executions** and inspect the error. Also check business email spam/junk and MailApp sending quota.
7. If the Google confirmation page shows an error, check **Apps Script → Executions** and confirm the deployed script has access to the linked sheet.

## Future updates

After editing `Code.gs`, use **Deploy → Manage deployments → Edit → New version → Deploy** to update the existing web app without changing its URL.

If you change the website HTML/CSS/JS, rerun this new `deploy-to-github-pages.sh` and paste the same deployed Google web app URL. **Never run the old FormSubmit deployment script**.

## Security and privacy

This form collects business contact details only. Do not request student data or sensitive personal information. The script is public for anonymous submissions, so the private Sheet is protected by Google Sheets permissions, but the endpoint may attract spam or exhaust Google quotas. It includes a hidden honeypot but no CAPTCHA/rate limiting. Monitor the Sheet and move to a managed form service if submission volume grows. Enquiries are emailed to the Northstar inbox and recorded in a Google Sheet. Data-handling privacy text on the website has been updated for this integration. **Do not make the spreadsheet publicly accessible.**
