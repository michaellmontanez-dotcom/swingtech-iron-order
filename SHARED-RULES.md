# SwingTECH — shared rules for every project

These rules apply to every SwingTECH project. Each project's own CLAUDE.md adds
project-specific details on top; if the two disagree, the project file wins.

## Who I am and how to talk to me
- I'm Michael, owner of SwingTECH Golf (club fitting, lessons, simulator, builds).
  I'm not a full-time developer: explain things in plain language, lead with what
  changed and what I need to do, skip jargon unless I ask.
- If a choice is genuinely mine to make (money, customers, anything public), ask.
  Otherwise pick the sensible option and tell me what you picked.

## Things that must never break
- **URLs never change.** Live links are bookmarked, on the website, and on the
  lobby TV. Keep the same Vercel alias / path; never rename a deployed project.
- **Payments never happen in our own apps.** Lightspeed (in-store) and Acuity
  (online, Stripe) own all payments. Never build checkout, card fields, or
  "mark as paid" logic.
- **Never invent numbers.** Prices, "value" figures, specs, stats, and customer
  data come from the real source (Lightspeed, Acuity, the clubs catalog, the
  database) or exact math on them — never estimated or made up.
- **Customer privacy.** Public screens (lobby TV, /welcome, booking page) show
  first name + last initial at most. Public APIs never return customer emails,
  phones, notes, or private appointment types.

## Brand
- Default look: accent forest green `#2e8b3a` (hover `#177a2c`, tint `#e8f5ec`),
  near-black `#000000` / `#0A0B0A`, white `#ffffff`, dark surfaces, Inter font
  with tabular numbers for prices and stats.
- These are the starting point, not a cage. When I ask to explore a different
  look, or a project's CLAUDE.md sets its own palette, it's fine to deviate.
  Don't change an existing app's colors on your own without asking.
- **The logo never changes.** It's a file in `~/Projects/stg-brand-assets/`. Copy it — never redraw,
  trace, approximate, or AI-generate a logo or icon.

## Secrets
- Never put passwords, API keys, or tokens in code or commits. 1Password
  ("SwingTECH Golf" vault) is the source of truth for every secret; apps get
  them through environment variables. Commit a `.env.example` with names only.
- New key or password: save it in 1Password first.
- Never print a secret's value in chat or logs.

## Where things live
- Code lives in `~/Projects/<repo>`, never in OneDrive.
- GitHub account: `michaellmontanez-dotcom`. Hosting: Vercel.
- The shared database is one Neon Postgres project (owned by
  swingtech-coaching-api). Each app only changes its own schema; any change to
  shared `public.*` tables is shown to me first as the exact SQL.

## Working style
- Read the project's CLAUDE.md and README before changing code.
- Keep changes focused on what I asked. Mention other problems you notice
  instead of fixing them uninvited.
- Before saying something works, actually run it (build, test, or load the page)
  and tell me what you checked. If you couldn't check, say so.
- Commit messages: one plain-English line saying what changed for the user,
  e.g. "Lobby: show first name + last initial on the welcome screen".
- Ask before anything hard to undo: deleting data, force-pushing, changing a
  live URL, editing production database tables, or sending texts/emails to
  customers.
- When a project's status or deploy steps change, update its CLAUDE.md so the
  next session knows.
