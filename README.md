> **Build v1.72-S83** · Fixed cut-off nacelles and off-kilter hull text — 2026-09-05

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
- **Step-by-step tutorial**: a dismissible coach card walks new captains through what to do in
  each phase, updating automatically as play advances. Veterans can switch it off from the
  header (🎓 TUTORIAL: ON/OFF) or dismiss it per-card.
- **Firing-chart hit outlook**: when you allocate power, every weapon shows a colour-coded
  hit-chance tag (VERY HIGH → OUT OF RNG) read straight from its FASA firing chart at the
  current range, with the exact d10 success band on hover — so you know before you commit
  whether a shot is worth the power. (It's a pre-movement estimate; closing the range changes
  it.)
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

## Recent fixes (v1.72-S83)

- **Fixed two real problems with last build's Constitution art**, both reported after the
  previous update: the warp nacelles were being cut off at the back end on both the tactical
  map icon and the damage-control screen, and the hull registry text was sitting too close
  to the front of the ship instead of along the side. Both corrected.

## Recent fixes (v1.71-S82)

- **USS Constitution's tactical sprite and damage-control art upgraded** using a
  high-resolution reference the user located, replacing the earlier lower-resolution
  versions.
- **Fixed the ship's hull registry text** on several views — it previously still showed
  the original stock art's placeholder name and number in a few places; now correctly
  reads "U.S.S. Constitution" / "NCC-1700" everywhere, including properly curved text
  where it wraps around the saucer section.

## Recent fixes (v1.70-S81)

- **The damage-control screen now shows real art for four more ships**: USS Constitution and
  all three Klingon Bird-of-Prey-hull ships. Every other ship still shows the generic
  schematic silhouette, unchanged.

## Recent fixes (v1.69-S80)

- **Fixed a real bug**: hiding in an asteroid field for cover, or firing through/into a
  nebula, previously showed a warning message about the effect but didn't actually change
  your odds of being hit — for either side. Both now genuinely make a shot harder to land:
  asteroid cover specifically weakens incoming beam weapons (not torpedoes, matching the
  rules), and nebulas degrade accuracy for whoever's shooting through one, or being shot at
  while inside one.

## Recent fixes (v1.67-S78 / v1.68-S79)

- **The damage-control screen can now show real ship art instead of the generic line-drawing
  silhouette**, on a per-ship basis. USS Excelsior is the first ship using this — every other
  ship still shows the same schematic silhouette as before, unchanged.

## Recent fixes (v1.66-S77)

- **Fixed the USS Excelsior's tactical map art**: the port side of the saucer section had a
  visible clipping defect. Repaired by mirroring the correct starboard side across the ship's
  true centerline.
- **The Excelsior now has real viewscreen art for the first time** — previously it used a
  generic fallback when targeted.

## Recent fixes (v1.65-S76)

- **Fixed a real bug**: any AI-controlled ship carrying both beam weapons and torpedoes/missiles
  could end up with "NaN" (not-a-number) shown for its shields and weapons power, which then
  corrupted its allocation for the rest of that fight. Torpedo-type weapons don't use the same
  power field as beams, and the AI's power-planning math wasn't accounting for that.
- **Legend-difficulty AI refined from real play**: after four combat logs of the user's own
  tactics, Legend now commits more power to movement when closing distance — matching how
  consistently the user prioritizes winning the initiative (moving last, reacting to the enemy)
  over other allocations in the same situation.

## Recent fixes (v1.64-S75)

- **The end-of-game narrative now reflects how many weapons were actually fired in the killing
  exchange**, not just the one that landed the final blow. Firing a single precise shot reads
  differently now from opening up with a full spread or an entire weapons bank — "a single
  torpedo," "a pair of shots," or "opened up with everything she had" depending on the size of
  the volley.
- **Found and confirmed why some playtest logs looked like the wrong difficulty**: the
  difficulty slider resets to Ensign on every new game (it doesn't remember your last choice),
  so it needs to be set again each time you start a match if you want something other than the
  default.

## Recent fixes (v1.63-S74)

- **Fixed the Klingon ships' viewscreen art**: the starboard gun rail was getting clipped when
  targeting one of these ships. Replaced with a clean source image; both gun rails now display
  correctly and match on the viewscreen.

## Recent fixes (v1.62-S73)

- **Replaced the Klingon ship art once more**: the previous update had one wingtip drawn with
  an extra weapon boom that the other wingtip didn't have. Traced this all the way back to the
  original reference image itself (not something introduced here) and replaced it with a
  corrected, symmetric source. All three ships now show matching detail on both wingtips.

## Recent fixes (v1.61-S72)

- **Fixed the new Klingon ship art from the last update**: the smallest details on the ships
  (their forward weapon booms) were getting accidentally erased during art processing, and the
  largest ship was sized slightly too big for its hex, causing it to overflow the edges.
  Both are fixed — full detail is preserved, and all three ships now fit correctly on the map.

## Recent fixes (v1.60-S71)

- **Three Klingon ships now have real ship art** — IKV Bird of Prey (small scout), IKV Stronger
  Bird (mid-size cruiser), and IKV Great Bird (frigate) all share one hull design at three
  different sizes, matching how they've always appeared on the tactical map, just with real
  artwork now instead of a generated silhouette. All three also got a real viewscreen portrait
  for the first time.

## Recent fixes (v1.59-S70)

- **Fixed a real bug**: a ship whose hull was actually destroyed used to stay fully visible on
  the tactical map after its explosion finished playing — nothing checked whether a ship still
  existed before drawing it. It now correctly disappears the moment it explodes, for either
  side. (Found from a playtest combat log — thank you to whoever's still sending these in.)

## Recent fixes (v1.58-S69)

- **Admiral-difficulty AI is smarter under pressure now**, fixed from a real playtest combat
  log: it now factors in its own hull damage (not just yours) when deciding how aggressive to
  be, stops "spending" power on weapon mounts that have already been destroyed, and re-checks
  that its heading actually keeps a surviving weapon pointed at you rather than just closing to
  a good range — previously a flanked Admiral-tier ship could sit there reporting "target not
  in arc" for several turns in a row without correcting for it.

## Recent fixes (v1.57-S68)

- **End-of-game screen redesigned** — the old full-screen VICTORY/DEFEAT overlay is gone. A
  compact panel now slides up from the bottom of the combat-log column only, so the tactical
  map stays completely visible through the end of the fight instead of being covered up.
  Includes a collapsible full narrative, a one-click combat-log download, turn/shot stats, and
  a New Mission button.
- **Ship destruction is a real, synced sequence now** — a detonation flash and glow, a fireball
  (built from the game's own explosion art) that grows over roughly a second and a half rather
  than staying a fixed size, and a shockwave that lights up individual hex edges sweeping out to
  the true blast-damage range from the FASA rulebook's own damage-from-explosions table. All
  three run off one shared clock so they read as a single event.
- **Fixed a real bug**: if both ships were destroyed in the same exchange (a true mutual kill),
  the result screen used to just say "DEFEAT." It now correctly shows "MUTUAL DESTRUCTION" and
  narrates both losses.

## Recent fixes (v1.56-S67)

- **USS Constitution (NCC-1700) now has real ship art** — a top-down tactical sprite and a
  bow-on viewscreen portrait, sourced from a fan reference sheet and relettered to this ship's
  own name/registry (the source depicted a different fictional ship). USS Enterprise
  (NCC-1701), which shares the Constitution class but not this specific art, is unaffected and
  still uses the procedural fallback as before.
- The reference sheet's other three views (profile, bottom-up, 3/4-rear) are relettered and
  saved in a separate `Constitution_integration.js` file for possible future use — not wired
  into the game yet.

## Recent fixes (v1.55-S66)

- **Per-phase tutorial coach** — new dismissible step-by-step guidance for new captains,
  covering Power / Tactical Advantage / Sensors / Movement / Firing / Repower, with a header
  on/off toggle for veterans. In-memory only (this file deliberately uses no browser storage).
- **Firing-chart hit outlook in Power Allocation** — each weapon now previews its chance to
  hit at the current range, colour-coded and read directly from the FASA firing chart (honoring
  both the chart and the weapon's max range), with the exact d10 band on hover.
- **Federation cloak-readout fix** — the relative-power-allocation sensor question no longer
  reports a cloaking-power line for ships that have no cloaking device. A Federation hull now
  correctly shows no cloak system at all; cloak-equipped Klingon/Romulan hulls still report it.
- **Boarding narrative** — the six power-kill capture narratives no longer use the awkward
  "crossed into the [X] hull" phrasing; each now opens with varied boarding language.

## Earlier fixes (v1.54-S65)

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
