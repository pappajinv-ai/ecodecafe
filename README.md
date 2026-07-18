# EcoDecafe - Deployment and Notes

This repository contains the GitHub Pages parent pages (index.html and admin.html) which embed the Apps Script web app in a responsive iframe, plus the app templates used by the Apps Script project (in the `app-templates/` folder).

Steps to finish setup

1. Deploy the Apps Script project using the `Code.gs` file in `app-templates/Code.gs` and `appsscript.json` scopes. In the Apps Script editor: Deploy → New deployment → Select "Web app".
   - Execute as: Me
   - Who has access: Anyone (even anonymous)
   - Copy the generated Web app (exec) URL.

2. Edit `index.html` and `admin.html` at the repo root and replace the placeholder `REPLACE_WITH_YOUR_APPS_SCRIPT_EXEC_URL` with the exec URL from step 1.

3. Push the changes (commit) and wait for GitHub Pages to serve the site at:
   https://pappajinv-ai.github.io/ecodecafe/
   Admin: https://pappajinv-ai.github.io/ecodecafe/admin.html

4. In your Google Spreadsheet, run the Apps Script function `setupSheets()` to create the required sheets. Use `createUser()` to create users (for example `createUser('net','Netedc@123','NETEDC-CAFETERIA')`).

Files added
- index.html (parent page embedding the Apps Script app)
- admin.html (parent admin embedding)
- app-templates/index.html (Apps Script template: data entry UI)
- app-templates/adminReport.html (Apps Script admin template)
- app-templates/shopPanel.html
- app-templates/adminReportPDF.html
- app-templates/shopReportPDF.html
- app-templates/Code.gs (Apps Script server code; adjust if necessary)
- README.md (this file)

Security note
- After testing, consider tightening postMessage origin checks (both parent and child) to the exact origins used, instead of using '*'.
