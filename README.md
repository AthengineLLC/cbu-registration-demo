# CBU Registration Demo

Clickable workflow demos for the team management app's registration system. Built as standalone HTML files (no build step, no dependencies) so they can be opened directly in a browser or transferred into the app.

## Pages

| File | What it is |
|---|---|
| `starter-template.html` | Copy this to start a new page |
| `CHEATSHEET.md` | Component reference. Source of truth for new pages. |
| `gallery.html` | Every component rendered, with the markup under it |
| `new-chat-prompt.md` | Kickoff prompt for a fresh claude.ai chat |
| `index.html` | Launcher, links to every demo |
| `admin.html` | Organization admin side: Registration Management dashboard, 10-step create/edit wizard, template builder with locked mandatory baseline, field/waiver libraries, subsection pricing, registrants dashboard with filtering, Comms messaging, archive |
| `registration.html` | Parent/player side: tryouts hub → individual tryout page → pre-pay registration flow (ticket + subsection or age-group pricing, player info, Parent 1/2, post-tryout contacts, waiver gate) → confirmation with the org's custom message |

## How to view

Open `index.html` in any browser, or deploy the folder to Vercel / GitHub Pages — every page is self-contained.

## Design standard

**New pages use the real app's design system.** Start from `starter-template.html`
and build only from the components in `CHEATSHEET.md`. Open `gallery.html` to see
them all rendered.

The styling is served live from the product at `https://cbu.athengine.com/proto.css`,
so a mockup built from these classes looks identical to what ships. Nothing is
copied or vendored, it cannot go stale.

The four existing demos below still use the older navy system (`#0c1327` background,
Oswald display type, CBU red actions). They are being absorbed into the app as-is, so
leave them alone. That system is preserved in `legacy/` for reference.

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
