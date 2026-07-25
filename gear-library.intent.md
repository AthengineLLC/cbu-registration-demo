# Screen: Jersey Packages (gear library)

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
