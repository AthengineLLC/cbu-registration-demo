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
  Team, Unassign (inline confirm), Start Evaluation (opens the eval form),
  and Log In As Player / Guardian grayed out until those accounts exist.
  Checkboxes allow bulk Change Team / Unassign.
- The EVALS tab is the audit hub, folded out of the old director and player
  audits. THE AUDIT IS PER SEASON - Addison wants as many evals as
  possible, so an eval from two summers ago never reads as covered. With
  the season filter on All seasons, each player is judged against their
  OWN current season (the unfiltered sweep answers "who is covered right
  now"); picking a season audits everyone against that season, including
  looking back at how complete a past summer ended up. Four summary counts
  (players shown, fully complete, partially done, nothing yet) over a
  table with one row per player - jersey number, player, team, the
  season's EVAL COUNT (complete is the floor; the count shows who stacks
  beyond it), then four status badges: Objectives (All 3 / Partial / Not
  Started), Coach Eval, Director Eval, and RATED. Rated is its own column
  because verbals-only evals are first-class - every rating slider can be
  skipped - and without the column an eval-without-rating would hide
  behind "eval done" and get forgotten. Fully complete = all three
  objectives + a coach eval + a director eval + at least one rating, all
  in the audited season. Coaches and directors are told apart by the
  directors list (Addison Maruszak, Nick James, Wayne Stofsky, Richie
  Warren, Maddux Faber). Every row carries Start Evaluation; the player
  name opens straight to the profile's Evals / Objectives tab.

# Screen: Add Stats (fourth tab on the player list)

- Who uses it: Addison / an admin after a season or tournament, holding a
  stats export (GameChanger or similar)
- What they are doing: importing a whole TEAM's stats at once from a CSV,
  tagged to a season and a team - deliberately simple for now: file in,
  tagged, stored
- What they see: Choose CSV File plus a downloadable CSV template; once a
  file is picked, a summary (name, row count, column count) and the
  columns split in two groups - the CORE columns the profiles display,
  and the STORED-ONLY columns
- THE RULE THAT MATTERS: keep every column we are given, always. Imports
  carry far more statistical depth than the profile shows; the profile
  displays the core hitting and pitching lines, but the full import is
  stored because the display set will change later and the data should
  already be in hand. An Import History list shows each run with its
  full column count as proof of that promise.
- What happens after: player rows land on the matching profiles' Stats
  tab (mocked - Isaiah carries seeded season lines)
- Out of scope for this pass: matching rows to players, fixing
  mismatched names, per-game lines, and editing past imports - Addison
  expects this page to get built out further later
- All profile and eval fields start empty / not applicable for real
  players - Isaiah Maruszak is demo-filled on purpose so every screen
  has something to show

# Screen: Eval writing flow (Start Evaluation, anywhere it appears)

- Who uses it: a coach or director, usually right after a tournament
  weekend, sometimes from the stands mid-event - typing or voice-dictating
  rough, because AI cleans it up later (see the three-layer rule below)
- What they are doing: writing up one player - either a FULL EVALUATION or
  a quick OBJECTIVES ONLY entry (a chip toggle at the top switches the
  form; this mirrors the old system's objectives-only toggle)
- Setup row: SEASON (auto-stamped with the player's current season,
  changeable for backfills - the audit runs per season so the stamp is
  what makes an eval count), evaluation date, and the type toggle. The
  evaluation auto-links to the signed-in staff member's name and role,
  like the college contact log - no evaluator dropdown.
- Objectives Only: the three development objectives as free text -
  Fundamental, Physical, Mental / Emotional. At least one is required.
- Full Evaluation: EVERY DIVIDER HAS ITS OWN INCLUDE SWITCH in its navy
  header, with a small white whisper next to the switch ("Toggle off to
  skip this section" / "Skipped - toggle on to include") so nobody has
  to guess what it does. Only Recruitment has no switch, because "Not
  projected yet" already is the off state. In order:
  1. Projected Positions - toggle chips (C 1B 2B 3B SS LF CF RF DH RHP
     LHP). ALWAYS STARTS BLANK - never prefilled from the roster
     positions, because the projection is the coach's own read, not an
     echo of what the family entered at registration. Where he
     PROJECTS, not where he plays today. FULLY OPTIONAL - leaving them
     blank is a fine answer and blocks nothing. Positions no longer
     drive which sections appear; nothing on the form is "smart"
     anymore.
  2. Performance Reports - FIVE categories, ALL always visible:
     Defensive, Offensive, Pitching, Base Running, Baseball IQ. Use the
     ones you saw, skip the rest - defensive only is a real eval. NO
     per-report dates - coaches will not remember them, so the one
     evaluation date in the setup row covers everything on the eval.
     A NOTING AN IMPROVEMENT toggle rides next to Add: it tags that
     report as an improvement, shown as a green Improvement Noted tag on
     the card (families see it too - it is good news). The tag is
     machine-readable on purpose: when the AI card generates, it can say
     "over the last six months your coach noted an improvement in..."
     and make the family feel the progress.
  3. Performance Ratings - TAP-TO-RATE DOTS, not sliders: a 1-10 dot
     track per row, FIVE rows always shown (Defense, Offense, Pitching,
     Base Running, Baseball IQ), each STARTING AS NOTHING. Addison's
     fear was a slider defaulting to 5 and getting submitted unnoticed -
     so a rating only exists once a dot is tapped ("Nothing yet" until
     then), the tapped dot fills in its band color, Clear takes it back
     to nothing, and Don't Rate Yet stays as the explicit version of the
     same call. A small red triangle sits UNDER THE 5 DOT labeled
     "Average For Age" - the scale explains itself on the track because
     most people do not read section copy. Untouched rows store nothing
     and keep the hub's Rated column open. All five ratings flow to the
     eval cards (DEF/OFF/PIT/BASE RUN/IQ badges) and the AI card tiles.
  4. Roster Level - same tap-to-rate dots, same starts-as-nothing rule,
     with its own triangle under the 5 dot labeled "Rostered Perfectly":
     1 = move way down, 5 = properly rostered, 10 = move way up.
     INTERNAL ALWAYS - never shows to the family even on a shared eval.
  5. Recruitment - Projected College Level dropdown (High Draft, Power 4
     D1, Mid Major D1, Lower Level D1, High Academic D1, D2, D3, High
     Academic D3, D1 JUCO, D2 JUCO, NAIA, Not A Prospect), optional.
- Who Sees This? - the share switch, asked ON the form: internal only
  (default) or shared with player and family. A SHARED submit detours
  through the FAMILY-VERSION REVIEW page before saving (see below); an
  internal submit saves straight away. Either way it lands on the
  player's Evals / Objectives tab with the new entry in its season group.

# The AI Scouting Card (modal over the profile, staff only)

- Ported from Addison's old view_evals card and cut to CBU branding: red
  header band (name, team + season, evals-this-season count, and the RED
  HAT + college chip when committed), dark navy body. Opens from the
  Recruiting tab AND from the profile header, where the admin action row
  runs in Addison's order: Change Team (outline), Start An Eval (red,
  white text), then "[First]'s AI Scouting Card" (navy, white text).
  Never visible to families or the public.
- CURRENT RATINGS, NOT CAREER AVERAGES - Addison's rule: growth is real,
  you cannot average a rating over years. Per metric (defense, offense,
  pitching, roster): the NEWEST rating anchors the number; ratings within
  about four months of it blend together; anything older is overridden
  and aged out (a rating from nine months ago dies the day a new one
  lands; one from four months ago coincides). The card says how many
  ratings fed each tile and how many aged out. Tiles color by the same
  1-3 red / 4-6 yellow / 7-10 green bands. A LAST EVAL date badge rides
  the section header so the reader knows what the numbers are built on -
  if a player went unevaluated for a stretch (injury year, missed
  summer), the tiles still show the last known ratings but the badge
  calls it out: plain when fresh, gold past six months ("getting
  stale"), red past a year ("over a year old"). FUTURE ALGORITHM SEAM,
  not built: evaluator weighting - e.g. a head coach's rating counting
  more than a guest coach's. The demo blends evenly.
- Consolidated positions and projected college level from the newest
  eval carrying them.
- METRIC DEVELOPMENT, in three windows the admin flips between: Last 6
  Months (default), Last Year, All Time. Per metric: the MOST RECENT
  mark (never best-of-window - a best from a year ago would hide a
  slide since), the hard delta vs where the window started (e.g. +10.0
  mph), and the percentage, as a green arrow badge for improvement or
  red for decline. Direction respects the metric: on the clocks
  (dashes, pop time) the DOWN arrow is the good one and still shows
  green. Fewer than two readings in a window = no trend claimed. A
  total-career average is deliberately not offered as an "analysis" -
  a kid measured from 7 to 18 always improves; All Time is there to
  show the development story, and the real prize later, once seasons
  of data pile up, is PACE analysis: improving ahead of, on, or behind
  the age curve. That future is noted on the card itself.
- COLLEGES IN COMMUNICATION, in TWO sections: the CBU Staff Log (hover a
  school to see WHO logged the contact, when, and the note - the admin
  needs to know who inputted the data) and the Player + Family Log
  (hover shows date + note only - no "who" needed, the player logged
  it). Chips carry division badges (D1 green, D2 blue, D3 gold, JUCO
  navy, NAIA red).
- AI SCOUTING SUMMARY: in the real app Claude reads the season's evals
  (staff versions), objectives, improvement tags, metrics, and college
  contacts, and writes a multi-paragraph scouting report in CBU's voice -
  profile, defense, offense, pitching, then a roster-fit recommendation,
  like Addison's previous build. Isaiah carries a pre-written sample of
  the output; players with evals but no sample show where it generates;
  players with no evals say so.

# The three-layer text rule (every written word on an eval)

- Every free-text field keeps three layers, decided with Addison:
  1. RAW - exactly what the coach typed or voice-dictated. Never shown
     to families, never deleted. It is the scouting truth, and keeping
     it means the record can be re-rendered any way forever.
  2. STAFF - the cleaned-up, fact-driven version staff reads: every
     detail kept, straight to the point, a little harsh where it needs
     to be. In the REAL APP, AI drafts this from raw AT WRITE TIME and
     the coach approves it while the game is still fresh - cleanup is
     never silent and never happens months later at read time. In the
     demo, staff starts as the raw text.
  3. FAMILY - delicate, constructive, well written; not sugar-coated,
     just put the way a good coach says a hard thing to a parent. It
     EXISTS ONLY once the coach shares the entry, and it is FROZEN at
     share time - AI drafts it, the coach reviews and edits it on the
     review step, and only the approved wording ever reaches the family.
     Never regenerated behind anyone's back: what a parent screenshots
     is something a human signed off on.
- Read-time AI is reserved for aggregates (staff summaries, the AI
  scouting card) - a lens over many records, never the record itself.
- On saved eval cards, staff see layer chips - Staff Version / Family
  Version (once shared) / Raw Notes (when it differs) - so the registers
  can be compared at a glance. Families only ever see the family layer.
- What happens after: the entry appears in its season group on the
  profile tab and moves the audit badges and Rated column on the hub.
- Out of scope: the coach-evaluation form (directors rating COACHES -
  game management, parent issues; that is the other half of the old
  coach_evals page and belongs with Coach Access), AI staff summaries,
  and eval editing after submit (remove and rewrite for now).

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
     internal-only or shared with player and family. Never public.
     Entries are GROUPED BY SEASON, current season on top, old seasons
     below as history - the file grows into a year-over-year development
     record. Within a season: Objectives entries (the three development
     objectives with author, role, and date), then Evaluations (season
     pill, positions if projected, colored 1-10 rating badges - Addison's
     bands: 1-3 red, 4-6 yellow, 7-10 green - roster level, projected
     college level, and the defensive / offensive / pitching reports,
     with a green Improvement Noted tag on reports flagged as
     improvements). Each
     entry shows who wrote it with a Director or Coach pill and its share
     state. Layer chips on a card flip its text between Staff Version,
     Family Version (once shared), and Raw Notes (when they differ).
     Flipping the share switch ON opens the FAMILY-VERSION REVIEW inline:
     every written text as an editable textarea (AI-drafted delicate in
     the real app), Approve & Share freezes the wording; flipping back to
     internal is instant. Remove sits behind an inline confirm. + New
     Evaluation in the section header and Start Evaluation on the header
     open the eval form.
  3. Recruiting - College Commitment (search schools, mark committed; the
     player flips to Committed system-wide and earns the RED HAT next to
     their name everywhere - Red Hat Nation), College Contact Log (log a
     college contact; it auto-links to the signed-in coach's name so staff
     can see who each college talks to), and two AI cards: the AI
     Scouting Card (our voice - LIVE as a modal now, spec in its own
     section below) and the AI Player Pitch (the player's voice - built
     from the colleges of interest, level of interest, and personal
     write-up the player fills out in the Player + Family view; AI turns
     it into the intro report colleges see). ADMIN LAYOUT: commitment
     top-left, the two AI cards stacked top-right (they never grow, so
     the top row stays symmetrical), and the contact log FULL-WIDTH AT
     THE BOTTOM - its list grows without limit and must never push
     anything down. Family layout unchanged.
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
  cannot add anything. Shared evals arrive as the FAMILY LAYER only (the
  delicate, coach-approved wording - never the raw notes or the staff
  version), with the roster level and all share controls stripped out;
  the tab copy tells them plainly that some evals stay internal to the
  staff and that is normal.
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
- Out of scope: real metrics, player/guardian logins, the public profile
  page, and wiring to Team Management's live rosters (mock data mirrors
  the same seasons and teams so the story lines up)
