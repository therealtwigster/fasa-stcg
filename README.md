> **Build v1.91-S102** · Fixed a real movement bug + added a minimize button for the results panel — 2026-09-06

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

## Recent fixes (v1.91-S102)

- **Fixed a real movement bug**: the "step forward/reverse one hex" button let a ship move
  directly into a planet or moon's hex, bypassing a check the normal click-to-move system
  already had. Both now correctly block that.
- **Added a minimize button to the victory/defeat panel** at the end of combat, so it can
  be collapsed out of the way to review the scrolled combat log and dice rolls underneath
  it instead of it blocking the view.
- Investigated the sensor-vs-firing report — confirmed this was expected behavior, not a
  bug: both systems check line of sight the same way, just at different moments as ships
  moved between phases. Also confirmed via the actual rulebook that ships are intentionally
  allowed to share a hex with each other (they just can't fire on each other while doing so).

## Recent fixes (v1.90-S101)

- **Applied your exact tuned settings from the design tool** to the live game — size,
  position, and the shield-arc/superstructure refinements. Also added rotation and
  horizontal positioning support to the actual game, which didn't exist before (only the
  tool had it).
- **Confirmed the ship-art system was never locked to one ship for all factions** — every
  faction already correctly shows its own ship's art, or a matching generic silhouette if
  that ship doesn't have custom art yet.
- **Fixed the design tool's layout bug**: the superstructure track was overlapping the
  shield arc line. It's now grouped with the other status displays instead.

## Recent fixes (v1.89-S100)

- **Actually fixed the K'tinga's missing boom and command pod this time.** After several
  builds guessing at sizing and rendering causes, checking the source image directly (as
  suggested) found the real problem: the picture itself had been cropped too tight from the
  very start, cutting off the command pod before any of that other work even happened. No
  amount of resizing could have fixed that. Re-cropped correctly from the original artwork,
  and the ship now displays complete in both the game and the design tool.

## Recent fixes (v1.88-S99)

- **Found and fixed the "invisible object" you spotted** — a real bug in the new design
  tool where the shield-arc sliders drew a tiny, incorrectly-sized hexagon right on top of
  the ship instead of the full-size one. Also fixed a box-height slider that wasn't
  connected to anything.
- **Added the two missing factions** (Gorn and Orion) to the tool, and fixed Klingon's
  color to match the game's actual red/crimson accent instead of green.
- **The K'tinga's damage-control ship is properly sized again** — now that the real
  visibility bug is fixed, there's no need for the overly-cautious small size from a few
  builds back.

## Recent fixes (v1.87-S98)

- **Found the actual cause of the missing boom/command pod** — it was never about
  positioning or the ship being cut off. It was an image-quality setting: thin details on a
  significantly shrunk image were rendering almost pure black instead of their real color.
  Fixed directly. The last few builds were unknowingly working around the wrong problem.
- **New tool**: `damage_control_designer.html` — a visual, interactive editor for the
  damage-control screen layout (ship size/position, shield arc shape and colors, status
  track sizing, faction color themes) intended as the template for every ship going forward,
  plus an early mockup of a crew-repair mechanic based on the original tabletop rules.

## Recent fixes (v1.86-S97)

- **The K'tinga's boom and command pod were still missing from the damage-control display**
  after the last fix. Investigated thoroughly but couldn't pin down exactly why the previous
  calculations didn't match what you were seeing — so rather than guess again, made the ship
  noticeably smaller and moved it further down to leave a much bigger safety margin. If this
  still isn't right, a screenshot zoomed in on just that panel (rather than the full screen)
  would help track down what's actually different about your setup.

## Recent fixes (v1.85-S96)

- **Redesigned the power and sensor status displays** — they previously looked like a solid
  block of color with no detail. They're now segmented indicator strips matching the style
  used elsewhere on the same screen, styled after the original tabletop game's own charts.
- **Fixed the K'tinga's boom and command pod still being clipped** near the top of the
  display — the ship is now sized and positioned more conservatively, and checked against
  many more window shapes this time to make sure it holds up.

## Recent fixes (v1.84-S95)

- **Fixed the damage-control panel showing completely blank.** Last build introduced a
  coding mistake that caused this screen to fail every single time it tried to draw — not
  an occasional glitch, a guaranteed failure. Found the exact cause, fixed it, and this time
  actually ran the updated code (not just checked that it was written correctly) against
  several realistic situations before considering it verified, specifically so a mistake
  like this is much less likely to reach you again.

## Recent fixes (v1.83-S94)

- **Fixed the K'tinga's damage-control art being shown backwards** — the ship's nose was
  pointing toward the aft marker instead of forward. This also explains why the ship looked
  cut off and why the power/sensor/hull displays looked like they were overlapping — with
  the ship reversed, its narrow front section was landing right on top of those displays.
  All from one root cause, now fixed.
- **Power and sensor status bars moved to the sides of the screen** instead of being
  crammed into the same crowded area as everything else.

## Recent fixes (v1.82-S93)

- **The K'tinga's damage-control art is much sharper** — turned out a higher-resolution
  source image was available and just wasn't being used.
- **Fixed the ship being too large and off-center** within its shield-arc display, and
  **fixed the shield arcs themselves overlapping each other** (the forward arc was crossing
  into the forward-port/starboard arcs) so all six now display cleanly with no overlap.
- **Added power and sensor status bars** to the damage-control panel — sensors status
  wasn't displaying at all before due to a data bug, and power status is now always visible
  instead of only appearing once a ship was badly damaged.

## Recent fixes (v1.81-S92)

- **Removed the ship-icon glow** added last build — that effect now only appears on the
  K'tinga's viewscreen (as originally intended), not on any ship's tactical map icon.
- **The K'tinga's damage-control screen now shows real ship art** instead of a generic
  placeholder silhouette — it had never actually been given its own damage-control image.

## Recent fixes (v1.80-S91)

- **Corrected a misunderstanding from the previous build.** "Red glow on Klingon torpedoes"
  meant the actual fired torpedo as it flies across the map, not an indicator on the ship
  itself. Fixed: Klingon KP-series missiles now fly red; everyone else's missiles and
  Klingon plasma torpedoes are unchanged. (The ship-icon glow from last build is still
  there for now — let us know if you'd like it removed.)

## Recent fixes (v1.79-S90)

- **Klingon torpedo tubes now glow on the tactical map**: any Klingon ship with an armed
  KP-series torpedo shows a small red glow near its bow, scaled appropriately for the map
  icon (not a giant copy of the viewscreen effect). Works for every Klingon ship with this
  weapon type, not just the K'tinga.
- **Damage-control shield status is now an actual drawn arc**, matching the same
  red/green/white style used on the tactical map, instead of just a colored text label.

## Recent fixes (v1.78-S89)

- **Fixed the damage-control screen cutting off the AFT section** of the ship — a real
  math error in the layout, not just a tight fit, meant part of the display was being
  drawn below the visible area on many window sizes.
- **Fixed the damage sparks/smoke effects to stay aligned** with the ship image after the
  above fix (they used slightly different, unsynced positioning math that would have gone
  visibly out of place otherwise).
- **Added a tooltip**: hovering over a ship on the tactical map now explains the red
  damage-tint circle that appears once a ship's hull drops below 60%.
- Investigated several other requests (torpedo glow on more Klingon ships, dimming Bussard
  collectors under low power, damage effects tied to specific damaged systems) — these are
  good ideas being tracked for a dedicated future update rather than a quick patch.

## Recent fixes (v1.77-S88)

- **Fixed jagged edges on the K'tinga's viewscreen image** — the source picture was a JPEG,
  and JPEG compression left faint speckled artifacts along the edges that the original
  background-removal missed. Cleaned up with a better method; edges are now smooth.
- **Fixed a real bug affecting every ship**: when an enemy was destroyed, the viewscreen kept
  showing it fully intact forever afterward, even though it had already exploded and
  disappeared from the tactical map. Now the viewscreen plays its own explosion and then
  shows a "contact destroyed" screen instead.

## Recent fixes (v1.76-S87)

- **Re-tuned the K'tinga's torpedo glow effect** — last build's version looked too big and
  diffuse. It's now a tighter, more clearly-defined glow, dialed in using a purpose-built
  tuning tool with live sliders rather than guessing at numbers repeatedly.

## Recent fixes (v1.75-S86)

- **Fixed the K'tinga (D-7 M/R/S) viewscreen art** — the previous image was a completely
  different art style from the rest of that ship's artwork (a photo-realistic render mixed
  in with an otherwise hand-drawn look). Replaced with a matching-style front view supplied
  by the user.
- **New feature: the forward torpedo tube now glows red on the viewscreen** when that
  weapon is armed and ready to fire. Currently only the K'tinga has this; more ships can
  get it added later.

## Recent fixes (v1.74-S85)

- **Fixed a real display bug affecting every ship**: the small F/S/P/A heading labels next
  to a ship on the tactical map could rotate (with the ship's facing) into the same spot as
  the ship's name below it, making a letter look like it was jammed into the name — this is
  what looked like a stray "S" in "USS Constitution". The two are now spaced further apart
  so this can't happen regardless of which way a ship is facing.
- **Fixed the Klingon D-7 ship-database entry**: marks M, R, and S were showing the older
  A/C/G artwork in the recognition-file viewer instead of their own correct (and different)
  refit-era look. Now shows the right art for whichever mark is selected.

## Recent fixes (v1.73-S84)

- **The Constitution's hull registry text needed to move further than last build's fix** —
  it's now clearly on the side of the saucer (roughly 8:30-9 o'clock if the bow is at 12),
  not close to the front anymore.
- Investigated a report of a hexagon-shaped ship-selection icon showing a stray extra "S" in
  "USS Constitution" — after a thorough search, this UI element doesn't appear to exist in
