# athengine design system cheatsheet

Every class below is real. It comes from the app's own stylesheet, served at
`https://cbu.athengine.com/proto.css`. If you use these class names, your mockup
looks exactly like the product.

Do not write CSS. Do not use hex colors. Use only what is on this page.

To see all of it rendered, open `gallery.html`.

---

## Page setup

Start from `starter-template.html`. Its `<head>` is not optional, keep it as is.

```html
<link rel="stylesheet" href="https://cbu.athengine.com/proto.css">
```

## Color tokens

Always `var(--token)`, never a hex code.

| Token | Use |
|---|---|
| `--bg` | page background |
| `--surface` | card background |
| `--surface-strong` | solid card background |
| `--surface-dark` | dark panels, code |
| `--text` | body text |
| `--muted` | secondary text |
| `--line` | borders |
| `--line-strong` | stronger borders |
| `--accent` | primary red, main actions |
| `--accent-deep` | pressed / darker red |
| `--navy` | table headers, dark chrome |
| `--gold` `--green` `--blue` | supporting colors |
| `--white` | white |

Type and shape: `var(--font-display)` for headlines (condensed, uppercase),
`var(--font-body)` for everything else, `var(--radius-card)` for corners.

## Buttons

```html
<button class="ui-button ui-button--primary" type="button">Save</button>
<a class="ui-button ui-button--primary" href="/players/new">New player</a>
```

Variants: `--primary` `--secondary` `--tertiary` `--danger`
Small: add `ui-button--sm` for buttons inside rows or tables.

`<a>` when it navigates. `<button type="button">` when it acts.

## Cards

```html
<section class="ui-card ui-card--pad-default">
  <header class="ui-card__header">Title</header>
  <p>Body</p>
</section>
```

Padding: `ui-card--pad-compact` `ui-card--pad-default` `ui-card--pad-spacious`
Add-ons: `ui-card--accent` (red bar down the left), `ui-card--interactive` (hover lift, for clickable cards)

`class="card"` is the older softer surface. List pages and detail sections use it.

## Badges

```html
<span class="ui-badge ui-badge--success">Active</span>
<span class="ui-badge ui-badge--warning ui-badge--sm">Owes</span>
```

Tones: `--neutral` `--info` `--success` `--warning` `--danger`. Add `ui-badge--sm` in tables.

## Stat tiles

```html
<div class="ui-stat-tile ui-stat-tile--success">
  <span class="ui-stat-tile__label">Collected</span>
  <span class="ui-stat-tile__value">$41,200</span>
  <span class="ui-stat-tile__delta">92% of expected</span>
</div>
```

Tones: `ui-stat-tile--neutral` `--success` `--alert`

## Summary strip

Dense stats row. Sits between a page header and a table.

```html
<dl class="ui-summary-strip">
  <div class="ui-summary-strip__item">
    <dt class="ui-summary-strip__label">Roster</dt><dd>22</dd>
  </div>
</dl>
```

Add `ui-summary-strip__item--zero` on an item to dim a zero value.

## Data table

The `ui-data-table__th` class on every `<th>` is what makes the header navy. Do not
forget it.

```html
<div class="ui-data-table__scroll">
  <table class="ui-data-table ui-data-table--zebra ui-data-table--hover">
    <caption class="ui-data-table__caption">Registrations</caption>
    <thead class="ui-data-table__head">
      <tr>
        <th scope="col" class="ui-data-table__th">Player</th>
        <th scope="col" class="ui-data-table__th ui-data-table__cell--right">Balance</th>
      </tr>
    </thead>
    <tbody class="ui-data-table__body">
      <tr>
        <td class="ui-data-table__td">Jalen Rivera</td>
        <td class="ui-data-table__td ui-data-table__cell--right">$450</td>
      </tr>
    </tbody>
  </table>
</div>
<p class="ui-count-badge">Showing all 3 players</p>
```

Alignment: `ui-data-table__cell--center` `ui-data-table__cell--right` (works on `th` and `td`)
No rows: `<td class="ui-data-table__empty" colspan="5">No rows</td>`

## Forms

```html
<label class="ui-field">
  <span class="ui-field__label">Player name<span class="ui-field__required">*</span></span>
  <input class="ui-input" type="text">
  <span class="ui-field__hint">Helper text.</span>
</label>
```

Error: add `ui-field--error` to the label, then
`<span class="ui-field__error" role="alert">Message</span>`

Controls: `ui-input` `ui-select` `ui-textarea`

Checkbox:
```html
<label class="ui-checkbox">
  <input class="ui-checkbox__input" type="checkbox">
  <span class="ui-checkbox__label">Liability release</span>
</label>
```

Group:
```html
<fieldset class="ui-fieldset">
  <legend class="ui-fieldset__legend">Waivers</legend>
</fieldset>
```

## Filter bar

```html
<div class="ui-filter-bar" role="search" aria-label="Filter players">
  <input class="ui-input" type="search" placeholder="Search">
  <select class="ui-select"><option>All teams</option></select>
  <button class="ui-button ui-button--secondary ui-button--sm" type="button">Clear</button>
</div>
```

## Empty state

Every list needs one.

```html
<div class="ui-empty-state">
  <h3 class="ui-empty-state__heading">No registrations yet</h3>
  <p class="ui-empty-state__description">Explain what lands here.</p>
  <div class="ui-empty-state__action">
    <a class="ui-button ui-button--primary" href="#">Open registration</a>
  </div>
</div>
```

## Detail section

How a detail page is chunked.

```html
<section class="card ui-detail-section">
  <div class="ui-detail-section__header">
    <div class="ui-detail-section__copy">
      <p class="ui-detail-section__kicker">Registration</p>
      <h2 class="ui-detail-section__title">Payment plan</h2>
    </div>
    <div class="ui-detail-section__actions">
      <button class="ui-button ui-button--secondary ui-button--sm" type="button">Edit</button>
    </div>
  </div>
  <div class="ui-detail-section__body">Content</div>
</section>
```

Collapsible: swap `section`/`div` for `details`/`summary`, use
`ui-detail-section__summary` on the summary, and drop the actions.

## List page

The standard shape of every index screen.

```html
<section class="card ui-list-page">
  <div class="ui-list-page__header">
    <div class="portal-page-hero-copy">
      <h1>Registrations</h1>
      <p>Everyone signed up for the fall season.</p>
    </div>
    <div class="ui-list-page__actions">
      <a class="ui-button ui-button--primary" href="#">New registration</a>
    </div>
  </div>
  <!-- summary strip, then filter bar, then count badge, then data table -->
</section>
```

## Baseball bits

Result pill and game tag colors come from per-org config, so set those two inline.
Everything else stays token driven.

```html
<span class="ui-result-pill" style="background:#166534;color:var(--white)">W 8-3</span>
<span class="ui-result-pill ui-result-pill--muted">T 4-4</span>
<span class="ui-result-pill ui-result-pill--none"> - </span>

<span class="ui-badge ui-game-tag ui-game-tag--muted">Pool play</span>
```

## Layout

There is no grid framework. These two cover almost everything.

```html
<div class="grid">        <!-- stacked, 16px gap -->
<div class="grid grid-2"> <!-- auto-fit columns, min 240px each -->
```

---

## When the system does not have what you need

Wizard steps, modals, chip filters, progress bars: these do not exist yet as
primitives. Build the closest thing out of cards, buttons and badges, then leave a
marker so Ben knows to build the real one:

```html
<!-- NEEDS: a 10-step wizard progress banner -->
```

Do not solve it with custom CSS. The marker list is genuinely useful, flag freely.
