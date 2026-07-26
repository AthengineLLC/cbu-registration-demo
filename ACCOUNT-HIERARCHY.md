# Account hierarchy (product context for every mockup)

This system is being built to sell to other travel organizations, not just
CBU. Every mockup in this repo should be read against this hierarchy. It
comes straight from Addison - treat it as the source of truth for who owns
what.

## The levels

1. **Developer** - Ben / the platform itself. Above everything.
2. **Organization** - the highest customer-level account. A travel org like
   CBU buys the system and runs it at this level. Org-wide settings live
   here and flow down.
3. **Affiliate** - organizations can have affiliates under them. An
   affiliate only sees its own jurisdiction: its teams, seasons,
   registrations, players. Never a sibling affiliate's.
4. **Team** - teams live under an affiliate. Coaches, rosters, schedules,
   team pages.

## What lives at the organization level

- **The gear library / jersey packages** (gear-library.html). The org is
  the "host jersey account": it enters every gear piece once - photo,
  title, price, size run.
- **Org settings** shown in the registration wizard: the fan gear store
  link and the external stores list.

## The inheritance rule (important)

When a new affiliate is created, the organization's gear library is
automatically loaded into that affiliate. Pieces (with their photos) added
at the org level filter down - the affiliate does not rebuild jerseys from
scratch. Affiliate registrations then pick from that inherited library the
same way the season registration wizard does today.

Open questions Addison has not decided yet (do not assume):
- Whether affiliates can add their own local pieces on top of the
  inherited ones, or edit/hide inherited pieces.
- Whether later changes to the org library re-sync to existing affiliates
  or only seed new ones.

## Metric verification (from Addison, July 2026)

Players are PLATFORM-LEVEL accounts (Athengine), not org property -
every travel org runs its own jurisdiction, but a player's identity and
metric history live with their account. When an organization runs a
metric testing day, it acts as the METRIC VERIFIER: a mark is stamped
with who recorded it and which org's testing day verified it, so a
number carries the weight of the organization behind it. Adding a
player to a testing day - including walk-ups - requires that the player
exists as an Athengine account first. Addison flagged this as a core
part of the platform story: "we need to be metric verifiers."

## Where the current mockups sit

CBU is playing both roles right now: Addison is the organization AND the
acting affiliate, so the mockups blend the two levels. Rough mapping for
when the real app splits them:

| Mockup piece | Real-app level |
|---|---|
| Jersey Packages / gear library | Organization |
| Fan gear store + external stores | Organization |
| Season/tryout registration wizards | Affiliate (using org-inherited gear) |
| Team Management, rosters, schedules | Affiliate / Team |
| Parent-facing pages | Families of a team |
