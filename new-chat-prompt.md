# New chat kickoff prompt

What changed: prototypes now use the real app's design system instead of our own
navy one. Your flow is the same, you just upload two files instead of one.

Upload `starter-template.html` **and** `CHEATSHEET.md` into the new chat, then
paste this and fill in the brackets.

---

I'm building another piece of the team management app for CBU Baseball.

The two attached files are the design standard:

- `CHEATSHEET.md` is the complete list of components I am allowed to use
- `starter-template.html` is what I start every page from

Build the new page from those. Hard rules:

1. Start from `starter-template.html`. Keep its `<head>` exactly as is, including
   the stylesheet link and the one small style block.
2. Use only class names that appear in `CHEATSHEET.md`. Do not invent classes.
3. Write no CSS. No extra `<style>` blocks. No inline `style` attributes, except
   the result pill and game tag colors the cheatsheet shows inline.
4. Never use a hex color. Use the `var(--token)` names from the cheatsheet.
5. No Tailwind, Bootstrap, or any CDN framework.
6. Never use `prompt()` or `confirm()`. All confirmations are inline.
7. Everything contained on mobile, no horizontal shifting.
8. No em-dashes or en-dashes in any copy. Use a hyphen or comma.
9. Real semantic HTML: `<table>` for tables, `<button>` for actions, `<a>` for
   navigation, `<label>` wrapping every form control.
10. If I need something the cheatsheet does not have (wizard steps, modals,
    progress bars), build the closest version out of cards, buttons and badges,
    and leave `<!-- NEEDS: description -->` above it. Do not solve it with custom
    CSS.

This is a clickable HTML demo with mock data, one standalone file my partner
transfers into the real app. It lives in the cbu-registration-demo repo and
deploys on Vercel, so name the file [page-name].html.

The piece I want to build: [WHAT IT IS, e.g. "a team schedule manager where an
admin creates games and practices and assigns them to teams"]

How it should work: [DESCRIBE THE FLOW STEP BY STEP: screens, buttons, what
happens when clicked. Voice-dictate this part if easier. Ask me questions if
anything is unclear before building.]

Also write a matching `[page-name].intent.md` with five bullets: who uses this
screen, what they are trying to do, what they see, what happens after, and what
is out of scope.

---

## The preview in the chat will look plain. That is expected.

claude.ai blocks outside stylesheets inside its preview pane, so the page it shows
you in the chat will look unstyled. Nothing is broken.

To see the real thing, do what you already do: save the file into the repo folder,
commit, push, then open it on cbu-registration-demo.vercel.app. It will be styled
there. Same for opening the file directly in your browser.

## Tips

- Look at `gallery.html` first, either open the file or go to
  cbu-registration-demo.vercel.app/gallery.html. It shows every component
  rendered with the markup under it. Fastest way to know what you can build with.
- One piece per chat. Come back to an old chat only to tweak files it already has
  loaded, otherwise upload fresh from the repo folder.
- When the piece connects to registration data (tickets, registrants, waivers),
  say so. Memory carries those structures.
- The intent file matters more than it looks. It is what Ben turns into actual
  build work. Without it he is guessing from your markup.
- Ship it the same way every time:

      git add .
      git commit -m "Add [piece]"
      git push

## Why it looks different now

It is beige, not navy. That is the real app's look, and the components in your
mockup are now literally the same ones in production. That means Ben wires up
what you designed instead of rebuilding it, which is a lot faster for both of us.

Your old navy template and prompt are still in `legacy/` if you need to look
something up. The five existing demos stay as they are.
