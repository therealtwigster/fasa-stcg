> **Build v1.54-S65** · Viewscreen, real ship art, new playable ship, AI fire pacing — 2026-09-01

# Star Trek: Tactical Command

A single-file, browser-based recreation of FASA's *Star Trek: Starship Tactical Combat
Simulator* — hex-grid ship-to-ship combat with power allocation, shields-by-facing, cloaking,
sensor locks, a live sensor-lock viewscreen, and a full Ship Recognition Database drawn from
the original recognition manuals.

**To play:** open `StarTrek_TacticalCommand_GAME.html` in any modern browser. No install,
no server, no external files — everything (including all ship sprite art) is embedded in the
one HTML file.

## What's in this build

- **5 playable factions**: Federation, Klingon Empire, Romulan Star Empire, Gorn Alliance,
  Orion Colonies — 45 ship hulls total, each statted directly from the FASA recognition
  manuals (power, shields, weapons, firing arcs).
- **Tactical viewscreen**: the enemy contact panel shows a live bow-on portrait of the ship
  you're facing instead of just text. No sensor lock yet? The portrait is genuinely blurred,
  overlaid with sensor static, and the status readout blinks like a warning light. Seven hulls
  (Reliant, D-10, Chandley, both D-7 marks, the Romulan Winged Defender, and Loknar) have real
  artwork; every other ship still shows a generated silhouette in its own faction's style.
  Federation, Klingon, Romulan, Orion, and Gorn each get distinct type, framing, and phrasing
  on this screen — not just a different color, a different instrument culture. Viewing as
  Federation also shows an independent transponder-signal readout, separate from sensor lock.
- **FASA-faithful turn structure**: Power Allocation → Tactical Advantage → three rounds of
  Sensors/Movement/Firing → Shield Repowering. Commit your power allocation, then confirm with
  **Proceed to Combat** or catch a mistake with **Revise Allocation** before the fight begins.
- **Multi-weapon volleys resolve one shot at a time**, staggered visibly, so you can actually
  watch a 3-disruptor Klingon broadside land instead of it flashing past in one instant.
- **Cloaking devices** on Klingon and Romulan hulls that have them historically — reserves
  power, drops your weapons offline for the turn, and breaks any lock on you.
- **5 AI difficulty levels**, Cadet through Admiral, with distinct movement and power-allocation
  behavior at each tier. The AI actively hunts you (including patrolling toward your last-known
  area when you're cloaked) rather than sitting idle.
- **Optional house rules** (off by default, toggle in scenario setup): Nebula fields, Planets
  & Moons (block movement/fire/sensors per FASA §13, including a mutual sensor shadow), and
  Gravity Wells.
- **Ship destruction**: a dying ship's remaining power becomes a FASA-rule blast that damages
  anything nearby, a short explosion animation plays before the result screen, and the victory
  screen narrates the killing blow along with turn and shots-fired statistics.
- **Ship Recognition Database**: browse all 78 catalogued hulls from the recognition manuals,
  including ones not yet flyable in-game, with full stat and weapon-loadout dossiers.

## Recent fixes (v1.54-S65)

- **Viewscreen, real ship art (7 hulls), and the Loknar-class frigate** — previously a
  dossier-only entry, now a fully playable Federation ship with FASA-derived stats.
- **AI multi-weapon volleys now stagger visibly** instead of resolving all at once.
- **Fixed a real bug**: a missed shot produced no visual effect at all — the beam/torpedo
  graphic was gated behind the hit check in the AI's fire-resolution function and only ever
  fired on a hit. Found via a user-submitted combat log; both fire functions (player and AI)
  now trigger the graphic unconditionally, with hit/miss only changing which effect plays.
- **`v1.53-S64`** — fixed a scenario-screen layout bug where a long ship name/class combo could
  overflow the ship-select dropdown and push its preview thumbnail out past the panel edge.

## Project files

- `StarTrek_TacticalCommand_GAME.html` — the game. This is the only file you need to play.
- `HANDOVER.md` — development state, open decisions, and backlog, for continuing work on the
  game in a fresh session.
- `check.js` — structural validator (single script/style tag, balanced braces, syntax check).
  Run with `node check.js StarTrek_TacticalCommand_GAME.html` before trusting any edited copy.
- `*_integration.js` (Reliant, D10, Chandley, D7, D7RSM, WingedDefender, LoknarClass) —
  reference bundles holding every extracted view for each ship's art, including angles not
  currently used in the game. Kept so that extraction work never has to be repeated if a future
  session wants a different angle or livery than what's currently wired in.

## Continuing development

See `HANDOVER.md` for the full technical state, including exact code locations for the ship
roster, weapon system, viewscreen, AI logic, and house rules, plus two genuinely open decisions
(Chandley's livery choice, a mark-naming mismatch against the FASA source) that didn't need
resolving before this build shipped but are worth knowing about. If you're picking this project
up in a new conversation, upload the current game HTML file, `HANDOVER.md`, and the FASA source
`.md` files together so the assistant works from your actual current build rather than a stale
copy.
