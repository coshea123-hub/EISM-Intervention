# GitHub + Google Sheets deployment

This repository contains a launch page. The full intervention interface runs on Apps Script and reads/writes the prepared Google Sheet. GitHub Pages does not host the backend or database.

## 1. Deploy the Google portal
Use the previously supplied EISM_Fast_Intervention_Portal.zip.
Create a NEW Apps Script project under your school Google account. Add Portal.gs, PortalIndex.html and appsscript.json as described in that package's README.
Deploy as a web app, execute as yourself, with access restricted to your school Workspace domain.
Run portalBenchmark and test the deployment with an administrator and mapped teacher account. Confirm denied users cannot read or save records.
Copy the deployed URL ending /exec.

## 2. Connect this launch page
Edit config.js and set webAppUrl to that /exec URL.
Do not place student records, exports, credentials or access tokens in this repository.
The empty configuration deliberately keeps the launch button hidden until deployment is ready.

## 3. Publish the launch page
In GitHub Settings > Pages, choose Deploy from a branch, main, / (root), then Save.
The expected launch address is https://coshea123-hub.github.io/EISM-Intervention/ once Pages is enabled and its build succeeds.
The repository is public; its launch page contains no student records. School access restrictions remain in the Google portal.

## Performance
The portal loads permitted profiles once into browser memory. Profile and subject switching is local; refresh and save require Apps Script calls.
GitHub hosts only the launch page, so this setup does not reduce Google's initial-load or save latency.
Do not use an iframe or anonymous deployment to bypass school sign-in.
