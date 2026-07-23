# CLAUDE.md

Clickable HTML prototypes for the CBU team management app. Standalone files, no
build step, no dependencies. Deployed on Vercel.

These mockups feed the real app (athengine). They exist so Ben can wire up a
designed screen instead of rebuilding it from scratch.

## Design system

**Read `CHEATSHEET.md` before writing any markup.** It is the complete list of
available components. `gallery.html` shows them all rendered.

The styling comes from the real app, served live at
`https://cbu.athengine.com/proto.css`. Every page links it. That is why a mockup
built from these classes looks identical to production.

## Hard rules

1. Start every new page from `starter-template.html`. Keep its `<head>` as is,
   including the stylesheet link.
2. **If `CHEATSHEET.md` has a component for it, use it.** Do not rebuild a card,
   button, badge, table, or form field that already exists, and do not restyle
   one.
3. **If you need something that is not in the cheatsheet, build it.** Do not
   contort existing components into a bad approximation. Build the right thing.
4. All new CSS goes in the `<style data-new-components>` block in the head.
   Nowhere else. No other `<style>` blocks, no inline `style` attributes except
   the result pill and game tag colors the cheatsheet shows inline.
5. **Comment every new component at its first use** (see below). This is how the
   design system grows.
6. Never use a hex color, including in new components. Use `var(--token)` names
   from the cheatsheet so new work inherits the org's branding.
7. No Tailwind, Bootstrap, or any CDN framework.
8. Never use `prompt()` or `confirm()`. All confirmations are inline.
9. Everything contained on mobile. No horizontal shifting.
10. No em-dashes or en-dashes in any copy. Use a hyphen or comma.
11. Do not set a `max-width` on text to control line length. Let containers do it.
12. Real semantic HTML: `<table>` for tables, `<button>` for actions, `<a>` for
    navigation, `<label>` wrapping every form control.

## Previewing

Open the `.html` file directly in a browser. It is styled straight away, no server
and no build needed. Pushing also deploys it to cbu-registration-demo.vercel.app.

If a page ever renders unstyled, the stylesheet link in the `<head>` is wrong or
was removed. Fix the link. Never "fix" it by inlining CSS into the page.

## Building something new

The design system does not cover everything yet. Wizard step banners, modals, chip
filters, progress bars, and drawers all have no primitive. Build them. A good new
component beats a bad approximation stitched out of cards.

Two things are required when you do.

**1. Comment it at its first use.** Ben reads these to decide what becomes a real
component in the app.

```html
<!-- NEW COMPONENT: wizard-steps
     A numbered progress banner across the top of a multi-step form.
     Nothing in the cheatsheet does this. -->
<ol class="wizard-steps">
  ...
</ol>
```

**2. Put its CSS in the one marked block**, which is already in the template:

```html
<style data-new-components>
  /* wizard-steps: numbered progress banner for multi-step forms */
  .wizard-steps { ... }
</style>
```

Keeping all novel CSS in one block means Ben can see at a glance exactly what is
new on the page and what came from the system.

Rules for new components:

- Use `var(--token)` colors, never hex, so they match the org's branding.
- Name classes plainly (`wizard-steps`, `modal`, `chip-filter`). Do not prefix
  them `ui-`, that prefix belongs to the real system.
- Reuse the existing tokens for radius, spacing and type rather than inventing
  new numbers where you can.
- Do not restyle or override an existing `ui-*` class to make a new thing. Build
  a new class next to it.

## Every page needs an intent file

Alongside `some-page.html`, write `some-page.intent.md`:

```markdown
# Screen: Season registration checkout

- Who uses it: a parent, on a phone, first time in our system
- What they are doing: paying the season fee and their annual profile fee
- What they see: fee breakdown, waivers to accept, card entry
- What happens after: profile created, redirected to their player page
- Out of scope: payment plans, sibling discounts
```

The HTML says what it looks like. This says what it is. It is what gets turned
into build work.

## Layout of this repo

| Path | What it is |
|---|---|
| `starter-template.html` | Copy this to start a new page |
| `CHEATSHEET.md` | The component reference. Source of truth. |
| `gallery.html` | Every component rendered, with markup |
| `new-chat-prompt.md` | How to kick off a new Claude Code session |
| `legacy/` | The old navy design system, kept for reference |
| `admin.html` `registration.html` `teams.html` `season-registration.html` | Existing demos, still on the old navy system. Leave them alone. |

## Do not

- Do not restyle the existing navy demos. They are mid-ingest into the app.
- Do not edit anything in `legacy/`.
- Do not add a build step, package.json, or framework. These are static files.
