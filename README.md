# CBU Registration Demo

Clickable workflow demos for the team management app's registration system. Built as standalone HTML files (no build step, no dependencies) so they can be opened directly in a browser or transferred into the app.

## Pages

| File | What it is |
|---|---|
| `index.html` | Launcher — links to both demos |
| `admin.html` | Organization admin side: Registration Management dashboard, 10-step create/edit wizard, template builder with locked mandatory baseline, field/waiver libraries, subsection pricing, registrants dashboard with filtering, Comms messaging, archive |
| `registration.html` | Parent/player side: tryouts hub → individual tryout page → pre-pay registration flow (ticket + subsection or age-group pricing, player info, Parent 1/2, post-tryout contacts, waiver gate) → confirmation with the org's custom message |

## How to view

Open `index.html` in any browser, or deploy the folder to Vercel / GitHub Pages — every page is self-contained.

## Design standard

All pages follow the CBU brand system: dark navy background (`#0c1327` → `#141d3a`) with white content cards, deep navy (`#0e1730`) section/table headers, CBU red `#b91e2d` primary actions with powder blue `#6daed4` as the Youth accent, Oswald condensed uppercase display type with Inter body text, pill badges, chevron step banners, chip filters, and big-number stat tiles. New pages should reuse these tokens.

## Key behaviors for implementation

- **Mandatory baseline**: every template starts with locked Player Information (name, birthdate, positions), Parent/Guardian 1 & 2 contact, and the red Post Tryout Contact Info section. Clubs add fields on top; they cannot remove the baseline.
- **Pricing rule**: a registrant's price = the price attached to their deepest selection (subsection if one exists, otherwise ticket, otherwise the flat price).
- **Registration form data**: a live registration's form = template + per-registration overrides (added fields, required/optional flips). Template edits do not retroactively change live registrations.
- **Waivers**: must be agreed to before payment; agreements are timestamped and stored against the registration.
- **Parent 2 on the player form**: only Parent/Guardian 1 shows at first — a button reveals the Parent 2 fields.
- **Post-tryout contact is a list** (one or both parents, or someone else) — Comms delivery resolves to these contacts.
- **Post-registration message**: written in wizard Step 9, rendered on the parent confirmation screen and included in the confirmation email.
- **Two-phase collection (future)**: keep the pre-pay flow minimal; detailed/extra fields move to a post-payment "Complete Athlete Profile" section.
- Avoid `prompt()`/`confirm()` in the real app — all confirmations are inline.

## Status

These are front-end demos with mock data. Databases, payments (Stripe), email delivery, and auth are wired by the app.
