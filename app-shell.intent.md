# Screen: App shell with sidebar navigation

- Who uses it: Addison, while designing; eventually mirrors what an org admin sees
- What they are doing: moving between the app's sections from one persistent
  sidebar instead of opening individual demo files
- What they see: a dark navy sidebar (org name, seven nav items, user card) with
  the selected section loading in the main area. Team Management and Registration
  Management load the existing demos; Dashboard, Player Management, Metrics Hub,
  Coach Access, and Settings show a "coming soon" panel until they are mocked up.
- What happens after: new sections get built and wired into the sidebar one at a
  time, so the whole flow is walkable in one place
- The sidebar is always present on admin pages: teams.html and admin.html
  redirect themselves into this shell when opened bare, and the shell accepts
  ?open=teams or ?open=admin to start on that section. Parent-facing pages
  (registration, season registration, team schedule) stay standalone on
  purpose - parents never see the admin menu.
- Out of scope: the athengine design system (this shell deliberately uses
  Addison's navy look), real routing, permissions per role
- Note for Ben: the sidebar structure (org header, nav order, active state, user
  card) matches the screenshot of the current app build; the styling is the navy
  demo system on purpose. Addison wants the app to look like this, not the
  current proto.css look.
