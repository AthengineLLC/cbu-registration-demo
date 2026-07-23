# New session kickoff prompt

What changed: prototypes now use the real app's design system instead of our own
navy one.

**Nothing changes in how you work.** Open Claude Code in this repo folder like
always. It reads `CLAUDE.md` on its own, which points it at `CHEATSHEET.md` and
the rules. You do not attach anything.

## First time, right after Ben updates the repo

Start a fresh session for this, not one that has been open building navy pages.
Claude Code loads `CLAUDE.md` when a session starts, and a long-running session
carries the old design in its head. Paste this once so it pulls, orients itself,
and reports the rules back so you can confirm it got them:

---

First, run `git pull` in this repo. Ben pushed a new design system.

Then read CLAUDE.md and CHEATSHEET.md, and look at starter-template.html and
gallery.html.

Then tell me back in a few lines:

1. What components already exist that you should use
2. What you do when I ask for something the design system does not have
3. Where new CSS goes, and what you leave in the markup when you build something new

Do not build anything yet.

---

If it says it will use the `ui-*` components from the cheatsheet, that new
components go in the `data-new-components` style block with a `NEW COMPONENT`
comment at first use, and that it never uses hex colors, it has it. Start building.

## Every piece after that

Just describe what you want. Something like:

---

Build a new page for the CBU team management app.

The piece: [WHAT IT IS, e.g. "a team schedule manager where an admin creates games
and practices and assigns them to teams"]

How it should work: [DESCRIBE THE FLOW STEP BY STEP: screens, buttons, what
happens when clicked. Voice-dictate this part if easier. Ask me questions if
anything is unclear before building.]

Save it as [page-name].html.

---

That is it. The design rules, the component list, and the intent-file requirement
are already in `CLAUDE.md`, so you do not have to repeat them every time.

## Tips

- Look at `gallery.html` first, either open the file or go to
  cbu-registration-demo.vercel.app/gallery.html. It shows every component
  rendered with the markup under it. Fastest way to see what you can build with.
- Build whatever the piece needs. If the design system does not cover it, it
  should build the new component and comment it so Ben sees it. The failure mode
  to watch for is the opposite: rebuilding a card or a button that already
  exists. Tell it to read `CHEATSHEET.md` if you see that.
- When the piece connects to registration data (tickets, registrants, waivers),
  say so.
- The intent file matters more than it looks. It is what Ben turns into actual
  build work. Without it he is guessing from your markup.
- Preview by opening the `.html` file in your browser. It is styled straight away,
  no server needed.
- Ship it the same way every time:

      git add .
      git commit -m "Add [piece]"
      git push

## Why it looks different now

It is beige, not navy. That is the real app's look, and the components in your
mockup are now literally the same ones in production. That means Ben wires up
what you designed instead of rebuilding it, which is a lot faster for both of us.

Your old navy template and prompt are still in `legacy/` if you need to look
something up. The four existing demos stay as they are.
