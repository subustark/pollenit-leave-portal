# PollenIT Leave Hub - Pilot

A ready-to-run leave portal based on PollenIT's Leave Policy (effective 01 April 2026) and Leave Application Form.

## Run it

Open PowerShell in this folder and run:

```powershell
npm start
```

Then open `http://localhost:3000` in your browser.

## Included

- Employee overview and earned leave balance (12 days annually)
- Leave application form with working-day calculation, contact details, reason, leave type, and emergency flag
- Three-working-day notice warning and LWP policy guidance
- Request history with approval status
- Manager demo view: approve or decline pending requests, plus a team availability view
- Policy page containing the rules extracted from the provided policy PDF
- Requests persist in the browser on the same device using local storage
- Individual sign-in with employee-specific leave requests and balances
- Shared server-side data, employee/manager/HR roles, and dual approval

## Demo controls

Pilot accounts use the real PollenIT work-email addresses provided. Initial temporary passwords are deliberately not stored in Git; provide them to each pilot user privately.

- `subramani.e@pollenit.com` - employee
- `lalit.choudhary@pollenit.com` - employee
- `vishal.lodha@pollenit.com` - employee
- `himanshu.lodha@pollenit.com` - Reporting Manager
- `admin@pollenit.com` - HR

Employee requests are sent to both the Reporting Manager and HR. A request becomes approved only when both approve; a rejection by either closes it. Requests automatically split into Earned Leave and LWP if the employee has no paid balance remaining.

## Production handoff

This is a working pilot. Its temporary credentials are seeded by the local server and are not suitable for an Internet-facing production service. Before publishing, replace the temporary-password flow with approved Microsoft 365 SSO, use a managed database, and configure an approved mail service. No actual Outlook emails are sent yet; approval notifications are stored in the portal data until Microsoft 365 consent is available.
