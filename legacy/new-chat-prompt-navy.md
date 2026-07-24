# New Chat Kickoff Prompt — CBU App Pieces

Drop `starter-template.html` into the new chat, then paste this (fill in the brackets):

---

I'm building another piece of the team management app for CBU Baseball.
The attached starter-template.html is our design standard — build the new
page from its exact CSS tokens and components (dark navy background, white
cards, CBU red primary actions, powder blue for Youth, Oswald/Inter,
pills, chevron steps, chips, stat tiles). Follow its brand rules: boxes
are for actions, typography is for facts; never use prompt() or confirm();
make sure everything is contained on mobile with no horizontal shifting.

This is a clickable HTML demo with mock data — one standalone file my
partner transfers into the real app. It will live in our
cbu-registration-demo repo and deploy on Vercel, so name the file
[page-name].html.

The piece I want to build: [WHAT IT IS — e.g. "a team schedule manager
where an admin creates games/practices and assigns them to teams"]

How it should work: [DESCRIBE THE FLOW STEP BY STEP — screens, buttons,
what happens when clicked. Voice-dictate this part if easier; ask me
questions if anything is unclear before building.]

---

## Tips

- One piece per chat. Come back to an old chat only to tweak files it
  already has loaded; otherwise upload the file from the repo folder.
- If you forget the starter file, paste the Vercel URL instead —
  cbu-registration-demo.vercel.app — and ask it to match that site's design.
- When the piece connects to registration data (tickets, registrants,
  waivers), say so — memory carries those structures.
- Ship it the same way every time:

    git add .
    git commit -m "Add [piece]"
    git push
