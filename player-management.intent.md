# Screen: Player Management

- Who uses it: Addison / an org or affiliate admin, at a desk, managing the
  whole player pool
- What they are doing: finding any player in the system fast, moving players
  between teams, unassigning them back to the pool, adding a walk-up player
  by hand, and working a player's internal profile
- What they see: a search bar with smart dependent filters in order -
  Season, then Grad Year (HS seasons) or Age Division (youth seasons), then
  Team, which only offers teams that survive the filters above it. Roster /
  Evals / Recruiting tabs and a table of every player. No Guardian column -
  Addison cut it from this level. Each row has a three-dot menu: Change
  Team, Unassign (inline confirm), Start Evaluation, and Log In As Player /
  Guardian grayed out until those accounts exist. Checkboxes allow bulk
  Change Team / Unassign.

# Screen: Internal player profile (opens from the list)

- Who uses it: admins and coaches. This is view 1 of 3: the player/family
  login sees nearly this same screen with their own edit rights, and a
  third PUBLIC recruiting profile only goes live if the player opts in
  from their own account (the header shows Public Profile: Off).
- Header: white card with a fixed 3:4 portrait photo. Families send any
  shape of photo, so every photo is cropped to this frame - drag to
  reposition, slider to zoom. Photos load from img/players/<first.last>.jpg
  or by dragging a file onto the frame. Name, positions, class, school,
  size, bats/throws, plus team/season/commitment/public-status pills.
- Tabs, in order:
  1. Player Overview - the profile IS the form: Baseball Info (positions,
     height, weight, bats, throws), Academics (high school, GPA, weighted
     GPA, SAT, ACT), Personal Info (city, state, and birthday as
     month/day/year selects - the birthday drives the age shown
     everywhere, and the public profile only ever shows the age, never
     the birthday), Contact (player email and phone plus TWO parent/
     guardian slots - first name, last name, email, phone each -
     mirroring how families register), read-only Assignment, and Jersey /
     Apparel Info (most recent jersey, shirt, and pants sizes on the gear
     library's size run). ALL sections are LOCKED by default because
     their values populate from what the player and family enter in
     their own system - each section header carries an Edit button at
     top right that unlocks just that section, with Save / Cancel. The
     header shows the current jersey number next to the name.
  2. Evals / Objectives - coach-written; every eval carries a share switch:
     internal-only or shared with player and family. Never public. Start
     Evaluation button stubs until the coaching side exists.
  3. Recruiting - College Commitment (search schools, mark committed; the
     player flips to Committed system-wide and earns the RED HAT next to
     their name everywhere - Red Hat Nation), College Contact Log (log a
     college contact; it auto-links to the signed-in coach's name so staff
     can see who each college talks to), and two AI cards: the AI
     Scouting Card (our voice - coach evals, metrics, recruiting
     activity; ports from Addison's previous build once evals + metrics
     feed it) and the AI Player Pitch (the player's voice - built from
     the colleges of interest, level of interest, and personal write-up
     the player fills out in the Player + Family view; AI turns it into
     the intro report colleges see).
  4. Metrics - log results and see the best mark plus history per metric.
     Running (10/30/60-yard dash, seconds to two decimals, lower wins),
     Defense (outfield/infield/catcher velo in mph to one decimal, higher
     wins; catcher pop time in seconds, lower wins), Pitching (fastball
     peak velo), Hitting (exit velo). The player's BEST marks - only for
     metrics with data - show as tiles on the profile header. Every
     metric gets a development line chart (hover a dot for its value and
     date; best mark in red), and one shared date filter - All Time /
     Last 6 Months / Last Year / Last 2 Years or a custom from-to range -
     narrows every chart at once. Header tiles stay all-time bests.
     Performance metrics (jump force, vertical in inches) come later.
  5. Stats - season-by-season hitting and pitching tables, newest season
     on top, with a Career totals row (counting stats summed, rate stats
     recomputed). Hitting: OPS/AVG/OBP/SLG then G AB R H 2B 3B HR RBI BB
     SO SB CS. Pitching: W L SV GP ERA IP H R ER 2B 3B HR BB IBB HBP SO
     AVG OPS WHIP. Wide tables scroll inside their wrapper on mobile.
     Imported per season; game-by-game lines may come later.
  6. Schedule - the player's current team schedule in two views:
     Tournament Schedule (one row per event - org, name, dates, city,
     Next Up tag on the closest one, records on finished ones, past
     behind Show Previous) and a month calendar with tap-for-details on
     games and practices. Unassigned players see an assign-first note.
  7. Videos - X-powered video library. Asks for the X account FIRST:
     storing video files is expensive, so videos live as posts on the
     player's X account and this tab attaches links. Each link gets a
     title, auto-stamps the date it was added, and takes tags in two
     tiers asked in order: Game Or Practice first (Game Video / Practice
     Video), then the skill tags below (Hitting, Pitching, Catching,
     Infield, Outfield, Base Running, Performance). Multiple picks are
     allowed in both tiers and the UI says so. The library filter uses
     the same two-tier layout and stacks - Game Video + Hitting = game
     at-bats only. Players add their own links from their login later.
  8. Social - the player's social links (X, Instagram, TikTok, YouTube),
     optional and family-entered, locked behind an Edit button. X is
     strongly recommended and is the same field that powers Videos.
- Sample player: always Isaiah Maruszak.
- Demo scaffolding: a dashed "View As" bar at the top of the page flips
  between the three audiences (Admin / Coach, Player + Family, Public
  Site) without logging in and out. The bar is not part of the real app.

# View 2: Player + Family (via the View As bar)

The same profile, re-permissioned for the family's login:
- Header: they can adjust the photo and EDIT THE NAME. Jersey number is
  locked - it comes from CBU's roster and jersey orders. No Change Team,
  no Start Evaluation. They see team, season/class, committed-or-not,
  and public-profile status.
- THE TWO BIG QUESTIONS live on the header in their own panel:
  1. "Do you want the profile public?" - a switch. Turning it ON opens a
     hard are-you-sure warning in plain words: it goes on the internet,
     anyone with the link can view it, that is the point (recruiting +
     easy family sharing), and not everything shows - contact info never
     does. Confirm or keep private.
  2. "Show metrics on the public profile?" - independent switch; profile
     can be public with metrics hidden.
  3. "Show academics on the public profile?" - independent switch; the
     public Academics tab exists only when this is on.
- Player Overview: fully editable (same per-section Edit buttons).
- Evals / Objectives: read-only - they see only what coaches share;
  cannot add anything.
- Recruiting layout: College Commitment sits alone as a full-width row
  on top, then two sub-tab buttons switch between College Targets and
  My College Contact Log - the log grows without limit, so it must
  never push the targets down the page.
  - My College Contact Log: their own log of colleges that reached out,
    one-row form - separate from CBU's internal log, which they cannot
    see.
  - College Targets opens with an INTERVIEW grouped in two parts,
    answers saving as they go:
  - Baseball Program: "What are you looking to get out of the baseball
    program?" (free text); the playing-time question as THREE BUTTONS
    (N/A / Willing To Sit And Earn It / I Want To Play Right Away) -
    picking either real answer pops a shield mindset note spelling out
    what the choice means (dream-school grinder with no portal plans vs
    wanting a genuine day-one opportunity wherever the right fit is);
    "Are you willing to play out of state?" as N/A / Yes / No buttons,
    where Yes reveals a follow-up box asking how far - a region to stay
    close to, or the farthest corner of the country; then the target
    lists - divisions (D1/D2/D3/NAIA/JUCO toggle chips), conferences
    (typed chips), colleges (searchable picker).
  - Academics: "Academically, what are you looking for out of a
    university?" (free text) and "Are you looking for a high-academic
    university?" as N/A / Yes / No buttons. Answering Yes reveals a
    follow-up: where do the grades and test scores stand - "They
    Already Show It" (shield note: transcript backs it up today) or
    "They Will - That Is The Goal" (shield note: still young, scores
    are building, eligibility is a stated goal).
  All of it feeds the coaches' recruiting work and the AI Player Pitch.
  No AI cards, no internal contact log.
- Metrics: sees everything (tiles, charts, date filter) - cannot log.
- Stats: sees everything - cannot import.
- Schedule: full view, nothing to add.
- Videos and Social: full capability, same as admin.

# View 3: Public Site (via the View As bar)

- If the family has not opted in, the page says "This Profile Is
  Private" - nothing shows.
- Once public: header with the portrait photo, name, jersey number, red
  hat if committed, and the baseball resume line (positions, class, AGE
  IN YEARS ONLY - never the birthday, school, hometown, size,
  bats/throws), pills for team, season, and commitment. If metrics are
  opted in, the best-mark tiles ride the header next to the photo.
- Tabs: Academics (ONLY if opted in - otherwise the tab does not exist),
  Metrics (only if opted in), then always Stats, Schedule, Videos,
  Social. No Player Overview, no Evals / Objectives, no Recruiting.
- Everything is read-only: videos can be watched and filtered but not
  added or removed; socials are links only; metrics have no logging.
- Never shown: contact info, birthday, guardians, evals, either contact
  log, targets, or the AI cards.
- Out of scope: the eval form itself, real metrics, player/guardian logins,
  the public profile page, and wiring to Team Management's live rosters
  (mock data mirrors the same seasons and teams so the story lines up)
