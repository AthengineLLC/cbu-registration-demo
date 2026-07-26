# Screen: Metrics Hub

- Who uses it: Addison / an org or affiliate admin. This is the org's home
  for metric testing: creating metric testing days, keeping the library of
  metrics to be tested, and studying every result across the org.
- Three pills under the title, same top-section-plus-pills structure as the
  other admin pages: Testing Days / Metrics To Be Tested / Dashboard.
- The mock data (seasons, teams, all 43 players, the nine standard metrics)
  is the same as player-management.html so the story lines up - Isaiah
  Maruszak's newest testing-day marks here ARE the best-mark tiles his
  profile header shows.

# Pill 1: Testing Days

- What they are doing: creating a metric testing day through a wizard, then
  opening a day to enter results in bulk.
- The list: one row per day - name and location, date, season stamp, which
  metrics ran (count plus the first few names), player count, and a results
  status (Upcoming / In Progress / Complete / Awaiting Results) with a
  "recorded x of y" line. Click anywhere on the row to open the day.
- THE WIZARD (+ Create A Testing Day), five steps, tryout-registration
  style:
  1. The Basics - name, date, location, season. The SEASON STAMP works like
     evals: results recorded on the day file under that season.
  2. Who Is Testing - team checkboxes for the chosen season (with per-team
     player counts), an unassigned-pool row, select all / clear, and a live
     total of how many players land on the grid.
  3. Metrics To Test - the library as a menu. THE STANDARD SET STARTS
     CHECKED because for the most part everybody tests the same metrics;
     custom and site metrics sit below, unchecked, picked only where the
     site has the gear (the Tampa force plate). This is the per-day pick
     Addison decided on: the library is the menu, the day is the order.
  4. Testing Numbers - two choice cards. Numbers exist because at the field
     you find "47", not a last name. Assign Now hands out 1..N
     alphabetically by last name (the check-in sheet order); Assign At
     Check-In leaves the column blank and the grid sorted by last name -
     the fallback ordering Addison called out - with a one-click
     assign-all available later on the grid.
  5. Review - everything on one card; Create opens the day's grid straight
     away.
- THE BULK ENTRY GRID (opening a day) - the heart of the page, modeled on
  the jersey-grid feel and built for a hundred-plus players:
  - Testing NUMBER column first, then player (last name first), then team,
    then one column per tested metric. Number and player columns are
    STICKY while the metric columns scroll - works on a phone at the
    field.
  - Values are typed straight into the cells and save as they go - no
    submit step. Entry works live at the event or the next day from a
    paper sheet; same screen either way. Blank cell = not tested, and a
    metric a player does not test just stays blank (a catcher-only metric
    never blocks anyone).
  - Search jumps to a TESTING NUMBER or a name; sort toggles between
    Testing Number and Last Name; a Missing Only chip shows who has not
    been recorded yet. Filtering hides rows in place so typing never
    loses focus.
  - A progress bar counts recorded players ("recorded" = at least one
    result). Numbers are editable inline per row for the check-in flow.
- FIELD ENTRY - the phone flow, because most entry happens on phones at
  the event and sideways scrolling is a nonstarter there. Phones open a
  day straight into it; a Field Entry / Full Grid toggle on the day
  header flips either way on any device (the grid stays the desk view
  of the same data). The flow, per Addison:
  - FILTER BY TEAM and FILTER BY GROUP at the top (Addison: the person
    at a station sits on one team or one age group all day and wants
    everyone else off their phone). Group means grad class on a HS day,
    age division on a youth day, options drawn from that day's roster.
    THE FILTER SHAPES EVERYTHING: the list, the PREV / NEXT order, and
    the jump fields all stay inside the filtered set - Next Player
    means the next kid in the group being run. Clearable back to All
    at any time; the same two filters ride the desktop grid.
  - TWO search fields under the filters - SEARCH BY NUMBER and SEARCH
    BY NAME as separate boxes (Addison's call; the grid's search is
    split the same way) - over a tap-list of players in TESTING-NUMBER
    ORDER (how a field runs), each row showing number, name, and an
    x-of-y recorded badge. Number search matches from the start of the
    number; the two fields combine.
  - THE PLAYER CARD IS A FULL-SCREEN SHEET over the list (Addison's
    popup instinct, after Next Player kept dumping him at the top of
    the page above the day header): the sheet scrolls on its own, Next
    always opens the new player at the top of the card with nothing
    above it, saving or expanding a metric halfway down never bounces
    the view, and closing the sheet lands back on the list exactly
    where it was left because the page underneath never moved.
  - The sheet carries its own JUMP TO NUMBER / JUMP TO NAME pair at the
    bottom: type the next kid's number and land on them without going
    back to the list - the station coach's flow when kids arrive out
    of order.
  - Tapping a player opens a one-column card: one big button per metric
    being tested that day. Tap a button and it EXPANDS IN PLACE - a big
    decimal-keyboard input and Save, no screen jumps.
  - A SAVED METRIC TURNS GREEN WITH A CHECK AND ITS VALUE on the button
    ("60-Yard Dash / check 6.62 sec") - Addison's idea, extended: proof
    it is in the system, no double-entry, and a fat-finger is visible
    and tappable to fix. A toast confirms every save by name.
  - PREV / NEXT PLAYER buttons at the TOP AND BOTTOM of the card
    (Addison's requirement), stepping in number order, so a station
    coach - the one with the stopwatch - chains kid after kid on one
    metric without re-searching. A SKIPPED STATION JUST STAYS BLANK;
    moving on never requires a value.
  - The testing number is editable on the card for the check-in flow,
    and the card shows x of y recorded.
  - Nothing in this mode ever scrolls left or right, on phone or iPad.
- SAVE AS YOU GO, NO END-OF-DAY SUBMIT - a design commitment, not demo
  convenience: every Save is its own write the moment the check turns
  green. A dead phone loses nothing; stations write independently; a
  day is never "open" or "unsubmitted".
- OFFLINE - Addison's field-with-no-internet case. The demo persists
  the whole entry state (marks, testing numbers, created days, added
  metrics) to the device's localStorage on every write, so a laptop at
  a field with no connection keeps everything through shutdowns and
  reopens. THE REAL-APP RULE this stands in for: each save commits to
  the device's local store immediately, and a sync queue uploads on
  its own the moment a connection appears - marks are tiny and
  one-player-one-metric, so catch-up sync is instant and stations
  never collide. (Demo caveat: localStorage is per browser per device;
  clearing browser data clears it.)
- TWO-STAGE SAVED STATE, Addison's peace-of-mind system, same language
  in both entry modes:
  1. CHECK MARK, green border, white field = saved on THIS DEVICE.
  2. CHECK MARK, fully green field = synced into CBU's system.
  Online, a fresh save shows stage 1 and sweeps to stage 2 moments
  later (simulated upload in the demo). Offline, marks HOLD at stage 1
  - surviving app restarts via localStorage - and sync themselves the
  moment the connection returns, with a "marks synced to CBU" toast.
  The offline toast says plainly "Saved on this device - will sync
  when internet returns". Seeded historical marks render as already
  synced. A legend line on both entry modes teaches the two states.
- Sample days: two complete 2025 days, a complete Spring 2026 day, a
  complete Spring YOUTH day (so the youth side of the leaderboard has
  real rows), the June 2026 day still in progress (Isaiah recorded, with
  his profile's best marks), an upcoming Fall youth day with no numbers
  assigned - it demos the check-in path - and a SUMMER 2018 day holding
  the alumni legends (below).
- THE ALUMNI LEGENDS - Addison asked for a number one of all time from
  years ago, so three players exist ONLY in the record books: Marcus
  Rivera (Class of 2019), whose 2018 dash times still top the 17U book
  over Isaiah; Dre Watkins (Class of 2018), tested the summer after
  graduating, so his fastball is the system's lone 18U mark - proof the
  rare division appears only because a mark exists; and Tommy Osuna
  (Class of 2024), who was 12 in 2018 and still holds the 12U records
  over the current youth kids. Alumni never appear in class pickers or
  short windows - only All Time surfaces them, with their 2018 dates
  reading gold (stale) next to their unbeaten marks.

# Pill 2: Metrics To Be Tested (the library)

- One org-level library in two deliberately separate sections - Addison's
  no-clutter rule:
  - STANDARD METRICS - the org core set, the same nine metrics the player
    profiles chart. What the whole org studies, loaded into every
    affiliate automatically.
  - CUSTOM & SITE METRICS - metrics a site adds because it has the gear
    (Vertical Jump and CMJ Peak Power exist because CBU Tampa HQ has a
    force plate). They roll up so the org always sees affiliate-created
    metrics, but they never sit inside the standard list.
- Each row: metric, category, unit, direction, how many testing days used
  it; custom rows also carry who added it, where, and when.
- DIRECTION HAS THREE ANSWERS, not two - Addison's call: lower wins (the
  clocks), higher wins (the velos), or DIRECTION NEUTRAL for metrics
  where better/worse does not apply. Body Weight is the seeded example:
  recorded and charted, never ranked.
- + Add A Metric: name, category, unit, decimals, and the direction
  question with all three buttons (Higher Is Better / Lower Is Better /
  Direction Doesn't Matter). New metrics land as CUSTOM and become
  pickable on every new testing day's wizard. Promoting one into the
  standard set is an org-level call - out of scope for now.

# Pill 3: Dashboard - two modes on a toggle

- Addison's call: leaderboard-style full analysis, no player cards - the
  player NAME clicks through to the profile, and the profile is the
  per-player dashboard.
- A NAME CLICK OPENS THE PLAYER'S METRICS TAB IN A NEW TAB (deep link
  through the app shell: ?open=player-management&player=<slug>&ptab=
  metrics). New tab on purpose - the dashboard stays put so the next
  name can be checked right after. Alumni names toast instead: the
  record keeps their mark, but the demo has no profile behind them.
- Two modes: SINGLE METRIC (one metric deep, the original view) and the
  CLASS LEADERBOARD (every metric across one line per player).

## Mode: Class Leaderboard

- HIGH SCHOOL AND YOUTH ARE SEPARATED BY A PROGRAM BUTTON, Addison's
  call - the two sides never mix on one board. The only thing that
  changes is what a cohort means: HS ranks by GRAD CLASS (2027, 2028,
  2029), youth ranks by AGE DIVISION (14U / 12U / 10U, derived from the
  same grad-year-to-age rule the rest of the app uses), because that is
  how the youth program is organized and how those families think. Same
  groupings, same math, same windows on both sides. The org sees both
  programs; an affiliate still ranks only its own players.
- APPLES TO APPLES, TWICE OVER - Addison's design, refined across two
  conversations:
  1. Cohorts are GRAD CLASSES on the HS side, AGE DIVISIONS on the
     youth side. A 2027 is only ever measured against 2027s - never an
     8-year-old against an 18-year-old.
  2. Inside a class, players rank in POSITION GROUPINGS, because one
     blended score would hand extra points to whoever tests extra
     stations (the catcher problem). The groupings: PITCHING (pure arm -
     fastball velo), INFIELD (infield velo + hitting + the dashes),
     OUTFIELD (outfield velo + hitting + dashes), CATCHING (catcher velo
     + pop time + hitting + dashes), and HITTING (pure bat - who the
     best hitters are). Position groups are arm + bat + legs; pitching
     and hitting stay pure.
- MEMBERSHIP COMES FROM THE DATA, not the roster: test catcher velo and
  you are in the catching rankings; a two-way kid holds a pitching score
  and an infield score. Running a dash alone does not put anyone in a
  position grouping - the signature metric does.
- One Excel-style row per player: rank, name, one column per grouping
  metric showing the mark plus "#place of n", then the GROUPING SCORE.
- THE MATH: each place is divided by how many players are ranked in that
  metric (Addison's "divided by the number of places there possibly
  are"), so 5th of 8 in pop time and 55th of 90 in the 60 compare
  honestly; the score is the average of those percentile places across
  the metrics the player has data in, shown 0-100. EQUAL WEIGHTS for
  now, on purpose - weighting some fields heavier comes later.
- NO SINGLE OVERALL SCORE across groupings - Addison chose groupings
  only; no number pretends a catcher and a pitcher are comparable. (His
  max-velo idea - count only the best throwing velo once - was for the
  blended score and dissolved with it.)
- RANKS USE THE MOST RECENT MARK in the window, never an old best. The
  window chips (6 months / year / all time / custom range) exist here
  precisely because a kid who has not tested in a year still shows a
  most-recent from way back - tighten the range to fence stale marks
  out, and any date over a year old reads gold.
- ALL TIME FLIPS THE LEADERBOARD INTO THE DIVISION RECORD BOOK (both
  views, Addison's call): an Age Division selector (the HS range, 14U
  to 18U) appears, smart-preselected from the selected grad class and
  the current season year, and the cohort becomes everyone who ever
  held a mark at that age. Shorter windows and Custom Range stay
  class-based - Addison's "everything stays the same except All Time".
- CBU STANDARD METRICS ONLY feed the scores - an affiliate's custom or
  site metric (and anything direction neutral) never touches a ranking.
- SCOPING: the org ranks across every affiliate; an affiliate ranks only
  its own players, and the real app adds a second line giving the
  player's org-wide place without exposing another affiliate's players.

## Mode: Single Metric
- The SAME PROGRAM BUTTON as the leaderboard - High School / Youth -
  because grad-year filters alone left the youth side invisible.
- High School: filters are metric, season, grad year, team, over the HS
  pool only.
- Youth: the filter is an AGE DIVISION, and the board becomes a
  DIVISION RECORD BOOK - Addison's favorite idea in the hub. A mark
  counts for the division the player was in THE DAY IT WAS MADE, so
  with All Time on, the best 12U sixty ever run at CBU stays on the
  12U board even when that kid is a high school junior - or gone ten
  years. The demo shows it working: the 14U board carries the current
  14U kids next to Class of 2029 players whose marks date from summer
  2025, when they were 14.
- HS + ALL TIME is the record book too: an Age Division selector (14U
  to 18U) appears only on the All Time chip, smart-preselected from
  the selected grad class and the current season year (in 2029 looking
  at 2030s, All Time preselects 17U), freely flippable, with a dynamic
  message saying exactly what the board means ("every 17U mark ever
  recorded, any class"). All other windows, including Custom Range,
  keep following the class - Addison's rule.
- HOW A MARK KNOWS ITS DIVISION: division = the testing day's SEASON
  YEAR + 18 - grad year. The season year comes from the day's season
  stamp, and a Fall stamp rolls HS classes forward - a Fall 2026 day
  makes the 2027s 18U, exactly as Addison described; 18U days will be
  rare and 18U only appears once such a mark exists. Youth fall stamps
  do not roll (youth divisions turn on the spring birthdate cutoff).
  So the 2027s' January marks are 17U marks forever, even looked up in
  the fall after they rolled to 18U. In the real app, the birthday on
  the player profile is the precision override for kids who do not
  match their grade; grad year is the default.
- DUAL LABELS: HS cohort pickers read "Class of 2027 (17U)" and the
  division part rolls itself each August.
- Division options appear from the data - 13U shows up the day a 13U
  mark exists, never before.
- Metric picker: grouped Standard by category, then Custom & Site
  Metrics in their own optgroup - the separation again.
- WINDOWS: the same recency language as the AI Scouting Card - Last 6
  Months (default) / Last Year / All Time - PLUS the custom from-to date
  range Addison asked for.
- Summary tiles: players with a mark, best in window (and who), average
  most recent, and how many are improving.
- The table: rank (by best mark in the window, direction aware), player,
  team, best in window, most recent (never best-of-window alone - a
  year-old best can hide a slide), trend, readings count. The TREND
  compares the most recent reading against where the window started: the
  arrow shows which way the number moved, the color says whether that
  direction is good - a falling 60 time is green. Fewer than two readings
  in the window claims no trend.
- DIRECTION-NEUTRAL metrics change the read: no rank, no best-in-window,
  no improving tile - the list goes alphabetical and window changes show
  in neutral navy, because calling a weight change green or red would be
  claiming something the metric does not say.
- SCOPING RULE stated on the page: at the organization level this sees
  every affiliate; an affiliate login only sees its own teams. The demo
  blends both roles because CBU is playing both (see
  ACCOUNT-HIERARCHY.md).

# What happens after

- Results entered here are what the profile Metrics tab charts and the AI
  Scouting Card's metric-development windows read - one data stream,
  three lenses.

# Decided with Addison, queued for the next pass (not built yet)

- WALK THE WIZARD TOGETHER first - Addison wants to review the create
  flow live - then bolt EDIT onto it: an Edit button on a day reopens
  the wizard prefilled; changing metrics adds or removes grid columns
  without losing entered marks. Delete gets decided during that
  walk-through.
- DUPLICATE TESTING NUMBERS: warn but allow. Typing a number already in
  use shows an inline warning naming who holds it ("#12 is Adams") in
  both entry modes; keeping it anyway stays possible, but never by
  accident.
- SOFT RANGE WARNINGS per metric: each metric carries a plausible range
  and an out-of-range value saves only after a confirm - one tap for a
  real outlier, a save for every fat-finger. The record books are only
  as good as the worst typo in them.
- EVERY MARK STAMPED with who entered it and when, like evals link to
  the signed-in staff member - the audit trail for suspicious numbers.
  The demo fakes the signed-in user.
- ADD PLAYERS TO A METRIC DAY, both paths: search the existing pool
  (was not in the picked teams - one tap adds them with the next
  number) and create-new for walk-ups. THE IDENTITY RULE, Addison's
  call: every player must exist as an ATHENGINE ACCOUNT - other travel
  orgs run their own systems, so the platform account is the identity,
  and the org running the day acts as the METRIC VERIFIER (see
  ACCOUNT-HIERARCHY.md). A mark carries the weight of who verified it.
- CSV / EQUIPMENT RESULTS IMPORT (force plate, Rapsodo exports): next
  pass, modeled exactly on the Add Stats importer - map the metric
  columns, keep every column stored.
- PRINTABLE CHECK-IN SHEET: ALWAYS ORGANIZED BY LAST NAME - Addison's
  rule, because numbers may be jumbled and you find a person by name,
  then read their number off the row. Number, name, team, a blank
  checkbox column, browser print dialog.

# Out of scope for this pass

- Duplicate testing-number warnings and printable check-in sheets.
- CSV import of results from equipment exports (force plate, Rapsodo) -
  the Add Stats importer is the pattern when it comes.
- Editing or deleting a testing day after creation.
- Promoting a custom metric into the standard set, and per-affiliate
  metric visibility rules beyond "org sees everything".
- Wiring hub results into player-management.html's in-memory data (each
  page seeds its own copy; the numbers agree by construction).
