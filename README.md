# Top Speed Appliance Repair — topspeedappliancerepair.com

The brand landing page for **topspeedappliancerepair.com** (Top Speed Appliance LLC).
A single static page — no build step. Plain HTML/CSS/JS in `index.html`.

## What's on the page

- Brand hero for Top Speed Appliance Repair (Broward County, same-day service)
- The 9 canonical services, how it works, real pricing terms, and coverage
  (65 tri-county cities; 12 core Broward cities match instantly, other area
  requests go to office review)
- A working booking form, Speedy AI and Track My Tech doors, the Cleanout
  Vents partner line, and doors to the rest of the Top Speed ecosystem
- SEO: canonical, Open Graph, JSON-LD LocalBusiness (no ratings/reviews —
  none are claimed anywhere on this site), `robots.txt`, `sitemap.xml`
- Analytics: GA4 property `G-30WFYN49DP` (the portfolio property)

## Booking — how it works

The form is the real Service OS intake, not a demo. It POSTs to the relative
path `/api/v1/speedy/book`, and `vercel.json` rewrites `/api/v1/*` to the
production Service OS API (`https://top-speed-service-os.vercel.app/api/v1/*`),
so the form works same-origin on any host with no CORS dependency.

Payload mirrors the proven guest-booking contract (`source: "WEB_FORM"`,
`via: "topspeedappliancerepair.com"`) with first-touch attribution captured
from the landing URL (utm_source / utm_medium / utm_campaign / gclid /
fbclid / msclkid). On success the customer sees the real `referenceCode`
from the API; area-review and out-of-area responses surface the API's
message honestly. No price or diagnostic fee from any response is ever
rendered.

## Deploy (Vercel)

1. Import this repo into Vercel as a new project (framework: Other / no
   build command; output is the repo root).
2. Connect the domain `topspeedappliancerepair.com` (and `www`) to the
   project and follow Vercel's DNS instructions at the registrar.
3. The `/api/v1` rewrite ships in `vercel.json` — nothing else to configure.

## Notes

- Phone: (844) 460-7038 · Hours: Mon–Fri 8am–7pm
- Office: 6810 N State Rd 7, Suite 341, Coconut Creek, FL 33073
- Pricing shown is the real residential structure only ($99 diagnostic
  credited toward an approved repair; $210 flat repair labor; $150 flat
  installation; parts/materials at written quote). Commercial work is
  custom-quoted via Appliance Pro and never carries the $99 diagnostic.
- Dryer vent cleaning is handled by the network partner Cleanout Vents —
  never quoted or booked on this page.
