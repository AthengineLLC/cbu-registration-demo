# Screen: Jersey Packages (gear libraries)

Two libraries on tabs: the JERSEY PACKAGE LIBRARY (pieces that build the
package - tagged to programs) and the EXTRA GEAR LIBRARY (optional merch
outside the package: dry fits, backpacks, bags - no program tags, empty
sizes = one-size). The wizard's Jersey Package items pick from the first;
its Season Add-Ons pick from (or one-click load) the second. Both charge
with the family's first payment, never spread across a plan.

- Who uses it: an ORGANIZATION-level admin (see ACCOUNT-HIERARCHY.md), on
  desktop, setting up the org's gear. This is the "host jersey account."
- What they are doing: managing the org's gear shop - every piece that can go
  in a jersey package, entered once as its own line item
- What they see: a grid of gear cards (square photo, piece title, extra-piece
  price, size chips) and an add/edit form with a drag-and-drop photo square,
  title, price, and a size builder: one-click presets (Jersey / Pants youth +
  adult run, Sock S-XL, Hat XS / S/M / M/L / L/XL) plus custom typed sizes,
  each removable as a chip
- What happens after: the season registration wizard picks FROM this library
  when building a jersey package, instead of items being typed in per season.
  That wiring is not built yet - this page is the library itself.
- Out of scope: the registration-wizard picker integration, inventory or
  stock counts, real image storage (photos are kept in-page as data URLs;
  mock items use emoji placeholder squares)
- Note for Ben: sidebar placement is top-level under Team Management for now -
  Addison has not decided where gear management finally lives. Size presets
  matter: jerseys and pants share the youth+adult run, socks and hats have
  their own shorter runs, and any custom size can be added besides.
- Hierarchy note (see ACCOUNT-HIERARCHY.md): this library is organization
  level. When a new affiliate is created, the org's library - pieces AND
  photos - auto-loads into that affiliate, and the affiliate's registrations
  pick from it. Whether affiliates can add or edit pieces locally, and
  whether org changes re-sync to existing affiliates, are open questions.
- Coverage rule (important for Ben): when program tags are enabled, EVERY
  team must belong to a tag - an untagged team's families would get only
  the all-teams pieces and no program jersey. The primary mechanism in the
  real app: choosing a program tag is a required field when CREATING a team
  in Team Management (only when tags are on), so a team added months after
  setup can never slip through untagged. The warnings mocked here (banner
  on this page with one-click add-to-tag, warning on the wizard's Jersey
  Package step, red pill on per-team links) are the safety net, not the
  primary flow. The "Demo: create a team without a tag" link fakes the
  new-team scenario so the warning flow can be walked.
