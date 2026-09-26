> **Build v2.37-S148** · New playable Romulan ship: the RIS Whitewind cruiser — completes the full FASA ship roster! — 2026-09-26

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
  Orion Colonies — 44 ship hulls total, each statted directly from the FASA recognition
  manuals (power, shields, weapons, firing arcs). Newest addition: the **USS Baker** (Mk II and
  Mk IV), a real FASA Class IX Destroyer.
- **Tactical viewscreen**: the enemy contact panel shows a live bow-on portrait of the ship
  you're facing instead of just text. No sensor lock yet? The portrait is genuinely blurred,
  overlaid with sensor static, and the status readout blinks like a warning light. 22 hulls now
  have real artwork (Reliant, D-10, Chandley, both D-7 marks, the Romulan Winged Defender,
  Bird of Prey, and Stormbird, Loknar, Excelsior, both Klingon Throne Seeker/Ever-Victorious
  hulls, three more Klingon Bird of Prey classes, the Klingon Sting Tongue, Constitution,
  Enterprise, Federation, Baker, both Orion ships — Wanderer and Lightning — and the new Klingon
  Little Killer); the Klingon Saber and Gull and all three Gorn ships still show a generated
  silhouette in their own faction's style. Federation, Klingon, Romulan, Orion, and Gorn each
  get distinct type, framing, and phrasing on this screen — not just a different color, a
  different instrument culture. Viewing as Federation also shows an independent
  transponder-signal readout, separate from sensor lock.
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

## Recent fixes (v2.37-S148)
- **New playable ship: RIS Whitewind (V-7, Class X Cruiser)** — a Romulan cruiser with a mixed
  weapons battery: two disruptors covering the port side, two more covering the aft-starboard
  quarter, two forward disruptors of a second type, three torpedoes (two forward, one aft), and
  a cloaking device. Its firing arcs are genuinely lopsided rather than mirrored side to side —
  a deliberate, unusual design straight from the source material. Comes with real ship art.
- **This completes every ship identified from the FASA Star Trek Starship Combat Simulator
  rulebook that wasn't already in the game.** Eight new ships have joined the fleet over the
  past few days: the Andor, Larson, Remora, Northampton, Nova, Graceful Flyer, Bright One, and
  now the Whitewind.

## Recent fixes (v2.36-S147)
- **New playable ship: RIS Gallant Wing (V-6, Class X Cruiser)** — a Romulan cruiser with six
  disruptors (a swivelling forward/port bank plus dedicated forward and starboard guns), a
  forward plasma torpedo, and a cloaking device. Comes with real ship art: a top-down tactical
  sprite and a bow-on viewscreen portrait.

## Recent fixes (v2.35-S146)
- **New playable ship: RIS Bright One (T-10, Class VI Destroyer)** — a Romulan raider with four
  disruptors in two swivelling pairs and a single forward torpedo. It's also the first of this
  batch of new ships to carry a real cloaking device. Comes with real ship art: a top-down
  tactical sprite and a bow-on viewscreen portrait.
- This is the sixth and final ship from the recent run of Romulan and Federation additions —
  the full set (Larson, Remora, Northampton, Nova, Graceful Flyer, Bright One) is now complete.

## Recent fixes (v2.34-S145)
- **New playable ship: RIS Graceful Flyer (CS-2, Class V Scout)** — a fast, lightly-armed Romulan
  scout with four disruptors in two swivelling banks covering the front and both flanks. It has no
  weapon at all covering its rear — a scout built to outrun trouble, not fight it out. Comes with
  real ship art: a top-down tactical sprite and a bow-on viewscreen portrait.
- **A mismatched "FASA Canonical" mark in the Ship Recognition Database has been fixed.** The star
  had been pointing at a version of this ship whose numbers didn't actually match the rulebook; it
  now correctly shows as a rulebook-confirmed hull without over-claiming which exact version.

## Recent fixes (v2.33-S144)
- **The RIS Nova's torpedo tubes now match the rulebook too.** One bank was a swivelling
  forward/starboard pair, not a single fixed starboard tube — a small but real difference in how
  it can defend that side. The Nova is now fully accurate to its source material.

## Recent fixes (v2.32-S143)
- **The RIS Nova's disruptor banks now match the real FASA rulebook exactly**, thanks to the player
  checking their own physical copy. Its firepower is forward-heavy rather than evenly spread: the bow
  arc alone is covered by four of its six banks, with the rest guarding the flanks and rear.
- Confirmed: the Nova has no cloaking device.

## Recent fixes (v2.31-S142)
- **New playable ship: RIS Nova (Z-1, Class XIII Battleship)** — the Romulan Star Empire's heaviest
  hull yet. Twelve disruptors give it full coverage in every direction, backed by eight plasma
  torpedoes forward, to both sides, and aft. Comes with a striking, real ship — a top-down tactical
  sprite and a bow-on viewscreen portrait.

## Recent fixes (v2.30-S141)
- **New playable ship: UFS Northampton (Class X Frigate)** — a Federation frigate with six phasers
  covering forward and both aft quarters, plus three forward torpedoes; its flanks are its weak
  point. Comes with real ship art: a top-down tactical sprite and a bow-on viewscreen portrait.

## Recent fixes (v2.29-S140)
- **New playable ship: UFS Remora (Class VII Escort)** — a Federation escort bristling with eight
  phasers in four swivelling pairs, though both of its aft quarters are blind spots. Comes with real
  ship art: a top-down tactical sprite and a bow-on viewscreen portrait.
- **A mismatched "FASA Canonical" mark in the Ship Recognition Database has been fixed.** The star
  on the Remora was pointing at the wrong version; it now correctly marks the version the rulebook
  prints.

## Recent fixes (v2.28-S139)
- **New playable ship: UFS Larson (Larson Mk VII, Class VII Destroyer)** — a Federation destroyer with
  six phasers (including a swivelling forward/port bank) and two forward torpedoes. Comes with real
  ship art: a top-down tactical sprite and a bow-on viewscreen portrait, from a user-supplied render.

## Recent fixes (v2.27-S138)
- **The USS Andor has real ship art.** A detailed top-down sprite on the tactical map and a
  bow-on viewscreen portrait (deflector glowing), replacing the generated silhouette. It also
  shows in the ship preview on the mission screen and in the Ship Recognition Database.

## Recent fixes (v2.26-S137)
- **FASA Canonical is now easy to spot in the Ship Recognition Database.** The exact version the
  rulebook prints gets a glowing blue ★ on its version line (e.g. "★ Mk II · Class IX · Cruiser"),
  and a blue **FASA CANONICAL** badge sits beside PLAYABLE. Viewing a different version of a
  rulebook ship? The badge tells you which version the rulebook prints instead. Works for
  single-version ships like the Andor too.

## Recent fixes (v2.25-S136)
- **New playable ship: USS Andor (Andor Mk II, Class IX Cruiser)** — the Federation's missile
  boat, straight from the FASA combat rulebook. Two forward phasers and **eight photon torpedo
  tubes**: four forward, one port, one starboard, two aft. Its weak spots are the aft quarters,
  which no tube covers. It uses the game's generated Federation silhouette until real ship art
  is added.
- **FASA Canonical marks in the Ship Recognition Database.** Every ship printed in the FASA
  Starship Combat rulebook now carries a **blue ★** — next to its name in the list, on its file
  header, and on the exact variant the rulebook prints (alongside the existing amber ★ for the
  catalog's default variant; one button can show both). Hover the star to see the rulebook page.

## Recent fixes (v2.24-S135)
- **Fixed: enemy ships could leave their rear guns switched off.** The AI powered its weapons in a
  fixed order, so ships whose aft guns come last — like the Klingon Little Killer — often never
  powered them. You could sit right behind one and never draw fire. From Lt. Cmdr difficulty up,
  the AI now powers the guns that can actually bear on you first. (Cadet and Ensign crews still
  make that rookie mistake, on purpose.)
- **The AI anticipates a faster opponent at close range** (Lt. Cmdr, Captain, Admiral). If you
  out-manoeuvred it last turn, it now puts more power into movement — within limits — instead
  of letting you swing onto its tail every turn. It only knows what you did last turn, never
  what you've just committed.
- Ship stats and weapons are unchanged.

## Recent fixes (v2.23-S134)
- **Nebulae have a new look: fine, wispy filaments** that spill well past their hexes, instead of
  soft billows.
- **Nebulae now roll instead of drifting.** Each cloud stays exactly where it is while currents
  inside it churn the mist around like a slow boil — some pockets barely stir, others churn hard.
- **Nebula lightning** flickers a little more often and a little brighter.
- As before, the dashed outline shows exactly which hexes count as nebula for the rules.

## Recent fixes (v2.22-S133)
- **Gravity wells look like black holes now.** Each one is a perfectly black shadow ringed by a
  thin photon ring, inside a slowly swirling accretion vortex in the well's own colour.
- **They bend light.** Stars and nebula gas right around a black hole are gravitationally lensed
  — pulled into arcs around the shadow — while the hex grid stays straight so the map is still
  easy to read.
- **A bold dashed outline marks every gravity-well hex**, so it's always clear exactly which hex
  is affected — the art spills over the edges, the rules don't.
- **The rules haven't changed:** a gravity well still costs 2 movement points to enter, and
  nothing more (for now — some fun ideas are bookmarked for later).

## Recent fixes (v2.21-S132)
- **Nebulae look like nebulae now.** Instead of hex-shaped tiles, each nebula is one soft,
  billowing cloud that spills naturally past the hex borders and slowly churns.
- **Faint lightning flickers inside the clouds** now and then — the flash lights up the gas
  itself, not the empty space around it. Bigger, denser clouds storm more often.
- **You always know exactly which hexes count.** Every hex that's actually nebula (for sensor and
  to-hit rules) has a dashed outline in the cloud's own colour, since the gas drifts past the
  real boundary.
- **Viewscreen:** only the enemy you're looking at being inside a nebula thins out the stars on
  the viewscreen now — your own position doesn't. A nebula-heavy map still dims the sky overall.

## Recent fixes (v2.20-S131)
- **The enemy-contact viewscreen now has stars behind the ship.** Mostly faint white pinpricks,
  a few red giants and blue-white stars, none larger than 7 pixels across — and the ship
  properly blocks the stars behind it. Each battle rolls its own sky.
- **The sky reacts to the battle.** Nebulae on the map thin out the stars you can see — one big
  dense cloud hides more than a small wisp, and if either ship is sitting inside a nebula, only
  the brightest stars punch through. Stars fade rather than blink out.
- **Stars drift with your speed.** The more power both ships put into movement, the faster the
  starfield slides past; if both ships hold still, so do the stars.
- No twinkling, on purpose — stars only twinkle through an atmosphere.
- The USS Constitution's viewscreen portrait had two stray dark smudges at its edge that would
  have blotted out stars; they're gone (the ship itself is untouched).

## Recent fixes (v2.19-S130)
- **New playable ship: IKV Little Killer (K-23), Klingon Class VII Escort** — the single K-23
  from the FASA rulebook. Six disruptors (two in a swivelling forward bank, two fixed forward, two
  aft) and no torpedoes, so it can bite back when flanked. Comes with a real top-down tactical
  sprite and a bow-on viewscreen portrait; the artist's glowing red "torpedo" light on the bow
  was painted out to match the ship's beams-only loadout. Also shows as flyable, with its
  picture, in the Ship Recognition Database.

## Recent fixes (v2.18-S129)
- **The Klingon Z-4 "Deathgame" defense outpost is in the Ship Recognition Database with real
  art** — the fourth and last of the fixed stations flagged as missing early in the project.
  Two extra views from its reference sheet (the station rotating, and a mobile/in-transit
  configuration with lit engines) were saved separately for a possible future feature, not
  added to the game.

## Recent fixes (v2.17-S128)
- **The Romulan X-3 "Aviary" border outpost now shows real art** in the Ship Recognition
  Database. Its existing entry was updated in place rather than duplicated.

## Recent fixes (v2.16-S127)
- **The Federation R-1 orbital defense outpost joins the Ship Recognition Database** with real
  art. Some of its source numbers are uncertain in the original scan and are shown as given,
  not smoothed over.

## Recent fixes (v2.15-S126)
- **New kind of entry: fixed stations.** Starbase Alamo, a Federation defense outpost, is now in
  the Ship Recognition Database with real art and full FASA stats (two marks). Stations are
  browse-only — they can't be flown, since they don't move.

## Recent fixes (v2.14-S125)
- **The Orion Lightning has real ship art** — top-down sprite and viewscreen portrait. That
  completes the Orion faction: both playable Orion ships now have full real artwork.

## Recent fixes (v2.13-S124)
- **The Orion Wanderer has real high-detail art** — a new top-down sprite plus its first-ever
  viewscreen portrait (it was showing a generated silhouette before).

## Recent fixes (v2.12-S123)

- **The AI flanking fix from the last build now also works at Lt. Commander difficulty** — a
  second combat log showed the same "can't turn back around after being flanked" problem
  happening one difficulty level down from where it was first fixed. Same fix, extended down.
  Ships with no rear weapons are supposed to have that weakness — the fix is about the AI
  reacting sensibly to it, never about changing the ship.

## Recent fixes (v2.11-S122)

- **Fixed a real AI weakness, confirmed by a player combat log**: ships with no rear-facing
  weapons (like the Enterprise-class) could get flanked and then just sit there taking hits
  without trying to turn and fight back, because the AI wasn't checking whether it could
  actually shoot from the direction it was facing — only whether that direction was roughly
  "toward the enemy." It now checks for real, and gives itself the extra maneuvering power
  needed to act on it, at Captain difficulty and above. Not yet confirmed in a live match —
  worth trying the same matchup again to see how it holds up.
- **Fixed the Enterprise's sprite extending past its hex** on the tactical map — same class of
  sizing fix as two earlier ships that had the same issue.

## Recent fixes (v2.10-S121)

- **The in-game ship browser was quietly showing wrong information** — one ship's picture was
  actually a generic placeholder image instead of its real artwork, and four other fully
  playable ships were listed as "not playable, no art" even though they're both. Fixed, and
  the checklist tool from v2.06-S117 now double-checks this every time it runs, so it can't
  quietly happen again.

## Recent fixes (v2.09-S120)

- **The Romulan Stormbird has a real viewscreen picture now** — the very first thing ever
  flagged as missing in this project, finally done. Colored to match its existing top-down
  picture, just toned down rather than fully vibrant, per request.

## Recent fixes (v2.08-S119)

- **The Federation "Dreadnought" (USS Federation) has real high-detail art now** — both its
  top-down sprite and its viewscreen portrait, replacing an older placeholder-quality image.

## Recent fixes (v2.07-S118)

- **The USS Enterprise has real high-detail art now** — both its top-down sprite and a
  brand-new viewscreen portrait (it never had one before, despite already having decent
  top-down art).

## Recent fixes (v2.06-S117)

- **New playable ship: USS Baker (NCC-2664), Mk II and Mk IV** — a real Federation Class IX
  Destroyer from the original FASA sourcebooks, not a made-up ship. Comes with its own top-down
  tactical sprite and viewscreen portrait, built from a fan reference sheet.
- **New checklist tool**: `generate_ship_art_master_list.py` builds an always-current, styled
  page showing every playable ship's art status (top-down sprite, viewscreen portrait, or
  still-generated silhouette) straight from the game file itself — no more manually keeping
  track of which ships still need art.

## Recent fixes (v2.05-S116)

- **The Klingon IKV Saber has real ship art now** — a new high-detail top-down sprite replacing
  the old placeholder. Its viewscreen portrait is still the generated version for now.

## Recent fixes (v2.04-S115)

- **The Klingon IKV Sting Tongue has real ship art for the first time** — both a top-down
  tactical sprite and a bow-on viewscreen portrait, built from a fan reference sheet.

## Recent fixes (v2.03-S114)

- **Actually fixed the Romulan Bird of Prey's viewscreen white-line halo** — a fix shipped
  under v2.00-S111 didn't fully hold, and you were right that it was still there. Found the
  real cause this time (leftover edge shading from the original reference image) and verified
  the fix by checking the actual finished picture against the viewscreen's real background
  before calling it done, not just trusting the code.

## Recent fixes (v2.02-S113)

- **The cloak/decloak visual effect now uses your final chosen look** — a concealment veil plus
  a sparkle burst, a radar-ping ring, and a distortion ripple, carried over exactly from the
  standalone design tool you tuned it in.

## Recent fixes (v2.01-S112)

- **Fixed cloaking so it behaves like the tabletop rules**: a cloaked ship now stays cloaked
  turn after turn until you actively decloak, instead of silently dropping every single turn
  and forcing you to re-pay the cloak cost just to stay hidden.

## Recent fixes (v2.00-S111)

- **Fixed a real targeting-indicator leak**: the firing-phase "target is in arc" highlight was
  showing through a cloak with no check at all. Now correctly hidden.
- **New cloak/decloak visual effect** — a brief shimmer plays when either side engages or drops
  a cloak (purely cosmetic, doesn't change detection).

## Recent fixes (v1.99-S110)

- **Fixed the Romulan Bird of Prey pointing the wrong way** in the ship-selection preview —
  it now matches every other ship's orientation convention there.

## Recent fixes (v1.98-S109)

- **The Romulan Bird of Prey (RIS Talon) has real ship art for the first time** — both a
  top-down sprite and a viewscreen portrait.

## Recent fixes (v1.97-S108)

- **Fixed a real bug**: destruction narratives referred to every ship as "she," including Gorn
  ships, which don't follow that naming convention. Now correctly pronoun'd per faction.
- Confirmed (for a future fix) that the Romulan Bird of Prey had no viewscreen art at all.

## Recent fixes (v1.96-S107)

- **Renamed a misnamed Federation ship** — the Excelsior-class ships were showing "USS Oracle"
  instead of their correct name.

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
  the current build. If you're seeing it, let us know exactly where/how you reached that
  screen so it can be tracked down.

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
- `Whitewind_art.zip` — the Whitewind's profile view, saved for later use.
- `GallantWing_art.zip` — the Gallant Wing's bottom, back and profile views, saved for later use.
- `BrightOne_art.zip` — every angle from both reference sheets supplied for this ship, including
  the earlier sheet's views that weren't used in the end, saved for the record.
- `CS2_art.zip` — the Graceful Flyer's profile view, saved for later use.
- `Nova_art.zip` — the Nova's profile, aft and bottom views, saved for later use.
- `Northampton_art.zip` — the Northampton's profile view, saved for later use.
- `Remora_art.zip` — the Remora's profile view, saved for later use.
- `Larson_art.zip` — the Larson's bottom, profile and aft views, saved for later use (the top and
  front views are already in the game).
- `Andor_art.zip` — all five views of the USS Andor (top, bottom, front, aft, profile) as transparent
  cut-outs, plus the two in-game images and the original sheet; the extra angles are saved for later use.
- `K23_LittleKiller_art.zip` — the K-23 art package (now embedded in the game as of v2.19-S130);
  kept for its archived aft, profile, and bottom views.
- `Z4_turning_profile_SAVED.png`, `Z4_mobile_deployed_config_SAVED.png` — extra Z-4 station views
  saved for a possible future station-movement feature; not used in the game.
- `generate_ship_art_master_list.py` — run this any time ship art changes. It reads the game
  file directly and produces `Ship_Art_Master_List.html`, a checklist of every playable ship's
  art status (top-down sprite, viewscreen portrait, or still-generated) so you always know
  what's left to source reference art for. Run it with `--fix-catalog` to also correct the
  in-game ship browser's own status flags against reality — full instructions are in its own
  `README_generate_ship_art_master_list.md`, kept alongside it (this tool lives in a separate
  tools folder, not the main project folder).

## Continuing development

See `HANDOVER.md` for the full technical state, including exact code locations for the ship
roster, weapon system, viewscreen, AI logic, and house rules, plus two genuinely open decisions
(Chandley's livery choice, a mark-naming mismatch against the FASA source) that didn't need
resolving before this build shipped but are worth knowing about. If you're picking this project
up in a new conversation, upload the current game HTML file, `HANDOVER.md`, and the FASA source
`.md` files together so the assistant works from your actual current build rather than a stale
copy. Easiest: keep the game HTML in the Project's files and replace it with each new build —
the assistant has no memory between conversations, so whatever is in the Project is what it
starts from.
