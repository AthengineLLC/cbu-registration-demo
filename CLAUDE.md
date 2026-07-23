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

1. Start every new page from `starter-template.html`. Keep its `<head>` exactly
   as is, including the stylesheet link and the single small style block.
2. Use only class names that appear in `CHEATSHEET.md`. Do not invent classes.
3. Write no CSS. No extra `<style>` blocks. No inline `style` attributes, except
   the result pill and game tag colors the cheatsheet shows inline.
4. Never use a hex color. Use `var(--token)` names from the cheatsheet.
5. No Tailwind, Bootstrap, or any CDN framework.
6. Never use `prompt()` or `confirm()`. All confirmations are inline.
7. Everything contained on mobile. No horizontal shifting.
8. No em-dashes or en-dashes in any copy. Use a hyphen or comma.
9. Do not set a `max-width` on text to control line length. Let containers do it.
10. Real semantic HTML: `<table>` for tables, `<button>` for actions, `<a>` for
    navigation, `<label>` wrapping every form control.

## Previewing

The stylesheet is loaded from an outside domain, so claude.ai's in-chat preview
pane will render the page unstyled. That is a sandbox restriction, not a bug. Open
the file directly in a browser, or push and view it on
cbu-registration-demo.vercel.app, to see it correctly.

Never "fix" this by inlining CSS into the page.

## Missing components

Wizard steps, modals, chip filters, and progress bars are not in the system yet.
Build the closest version out of cards, buttons and badges, then leave a marker:

```html
<!-- NEEDS: a 10-step wizard progress banner -->
```

Do not solve it with custom CSS. That marker list is how new primitives get built.

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
| `new-chat-prompt.md` | Kickoff prompt for a fresh claude.ai chat |
| `legacy/` | The old navy design system, kept for reference |
| `admin.html` `registration.html` `teams.html` `season-registration.html` | Existing demos, still on the old navy system. Leave them alone. |

## Do not

- Do not restyle the existing navy demos. They are mid-ingest into the app.
- Do not edit anything in `legacy/`.
- Do not add a build step, package.json, or framework. These are static files.
