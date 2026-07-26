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
     you find "47", not a last name. ASSIGN NOW numbers in
     CLASS-AND-TEAM BLOCKS - Addison's rule from walking the wizard:
     oldest class or age group first, team by team inside it,
     alphabetical inside each team, so Team One runs 1-10, Team Two
     11-20, and the next class continues from there - with a STARTING
     NUMBER the admin chooses. Numbers are PENCILED IN: editing the
     day's teams reshuffles them freely, but ONCE CHECK-IN STARTS THEY
     LOCK (enforced when day editing gets built). Any single number can
     always be typed over by hand. Assign At Check-In leaves the column
     blank and the grid sorted by last name - the fallback ordering
     Addison called out - with a one-click assign-all available later
     on the grid.
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
- START METRIC DAY - the number-locking switch, from Addison's live
  walk-through. Before the day starts, numbers are penciled in: the
  RENUMBER tool takes a new starting number and re-populates everyone
  IN THE SAME ORDER THEY ALREADY HOLD (manual tweaks included), so
  "start at 15 instead" is one click, never a hand-edit of every row.
  Pressing Start Metric Day locks the numbers: from then on, changing
  any number pops an inline are-you-sure naming the player and both
  numbers ("change Adams from #12 to #14?") - because sometimes you
  really do mean it. Seeded past and in-progress days are started;
  the upcoming youth day and new wizard days are not.
- CLOSE OUT DAY - the day's finish line, a big green button that stands
  apart from the small management buttons on purpose (Addison asked
  for prominence). Behind an inline confirm; closing LOCKS EVERY FIELD
  - marks and numbers disabled in both entry modes, Add / Remove /
  Start / Renumber all gone - and the day reads "Closed Out" on the
  list. EDIT DAY is the only way back in, behind the warning Addison
  specified: "You will be editing recorded data." Reopening returns
  the day to started (numbers still locked) with Close Out offered
  again. The full day lifecycle: penciled-in, started, closed out.
  Seeded historical days ship closed - old days are read-only archives
  unless deliberately reopened.
- UNSTART (behind an inline are-you-sure): flips a started day back to
  penciled-in. RECORDED MARKS ARE NEVER TOUCHED - saves are per-player
  writes, so everything is right there when the day starts again.
  Usually an unstarted day has no data; when it does, it is kept.
- ADD PLAYERS TO AN EXISTING DAY (built from Addison's walk-through) -
  an Add Players button on the day header, before or after start:
  - Add A Whole Team: any pool-season team the wizard did not pick.
  - Add A Player: search the day's season pool; players already on
    the day are excluded and re-adding is a no-op.
  - THE NUMBERING RULE SPLITS ON STARTED: before start, additions
    reshuffle the penciled-in numbers into their class-and-team
    blocks; after start, a late addition takes THE NEXT UNUSED NUMBER
    (their team may hold 1-10, the latecomer is #99) and nobody else
    moves. Creating brand-new walk-ups still waits on the Athengine
    account rule.
- REMOVE PLAYERS FROM A DAY (the other half of the loop, NON-COMPLETED
  days only - completed history is untouchable): a Remove Players
  button opens a panel with the attending teams as removable chips
  (un-pick a team and all its players come off) and a scrollable,
  searchable roster list with a Remove per row. EVERY REMOVAL
  DOUBLE-CONFIRMS, naming the player or team and warning when recorded
  marks will be deleted with them. A FINISH button closes the panel
  back to the normal view. Numbers follow the same law as adding:
  before start, the penciled-in blocks reshuffle as players come off;
  on a started day, removals leave gaps and nobody else moves.
- DUPLICATE NUMBERS warn but allow (built with the above): giving a
  number another player already holds fires a heads-up toast naming
  who has it, and keeps your entry.
- PRINT CHECK-IN SHEET - a button on every day. Clean black-and-white
  table: number, LAST NAME, first name, team, and a blank checked-in
  box per row. ALWAYS ORDERED BY LAST NAME, Addison's rule - numbers
  may be jumbled, you find a person by name and read their number off
  the row. Prints through the browser dialog via a print-only overlay.
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

# The data-trust layer (built)

- OUT-OF-RANGE REVIEW - Addison's design, replacing the earlier
  block-at-entry idea: every metric carries a plausible range. An
  out-of-range entry SAVES (warn, never block - a toast says it will
  be flagged), and ONCE THE DAY COMPLETES OR CLOSES, a gold warning
  appears under Results: "3 marks look out of range - review". Click
  in for the queue: each flagged mark shows player, value, the usual
  range, and who entered it, with two resolutions - CONFIRM AS IS
  (a human vouches for the outlier; the record book keeps it) or
  CHANGE AND CONFIRM. Re-entering a confirmed cell re-flags it. The
  review works even on closed days - it is the supervised QA path.
  THE LIST SCREEN CARRIES A WARNING ICON too (Addison's ask): a gold
  badge with the flag count next to the day's status pill - hover says
  "Possible bad data - needs confirmation", click lands straight in
  that day's review. The REVIEW PANEL IS BOXED IN LIGHT RED with a red
  border (Addison kept clicking review and looking further down the
  page - now it cannot be missed, and opening any header panel scrolls
  the page to it). Resolving steps through: fix or confirm one and the
  toast counts down ("1 more to review"), the next row is right there,
  and the last resolution announces "all flags cleared" - banner and
  list icon both disappear.
  DEMO FLAGS SHIP SEEDED so the process can be walked cold: Trey
  Glaser's 10-yard dash on the closed Spring Testing Day reads 16.1 -
  the classic decimal slip for 1.61 - and the closed Fall 2025 day
  carries TWO (Thompson's exit velo missing a digit at 9.2, Ross's
  fastball with an extra at 855), all stamped with enterer and date,
  so both the single-flag and the step-through multi-flag flows are
  demonstrable.
- EVERY MARK STAMPED with who entered it and when (the signed-in user,
  like evals) - shown in the review queue and on the field-entry
  panel. The audit trail for the day a number looks wrong.
- EDIT DETAILS on any open day: name, date, location, and the metric
  list. Removing a metric hides its column but KEEPS recorded marks -
  they reappear if it is re-added (confirm states this).
- CSV IMPORT (Import From CSV, after Print on the day header):
  affiliate tech exports - force plate, Rapsodo. Pick the file, tag
  which column identifies the player (testing number or name - a row
  is a player) and which columns feed which datafields; headers are
  auto-guessed, always overridable. Imported marks are stamped,
  sync-queued, and range-checked like hand entry. Unmatched rows are
  REPORTED by name/number, never silently dropped - fix the file and
  re-import.
- WALK-UP ACCOUNT CREATION: OMITTED, Addison's call. Worst case the
  player registers for the team and lands in the pool. The Athengine
  identity / metric-verifier rule stands (see ACCOUNT-HIERARCHY.md)
  for how the real app treats player accounts.

# Out of scope for this pass

- Duplicate testing-number warnings and printable check-in sheets.
- CSV import of results from equipment exports (force plate, Rapsodo) -
  the Add Stats importer is the pattern when it comes.
- Editing or deleting a testing day after creation.
- Promoting a custom metric into the standard set, and per-affiliate
  metric visibility rules beyond "org sees everything".
- Wiring hub results into player-management.html's in-memory data (each
  page seeds its own copy; the numbers agree by construction).
