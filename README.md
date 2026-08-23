# Star Trek: Tactical Command

**Build v1.52-S63**

A hex-grid starship combat simulator built on the FASA *Star Trek: Starship Tactical Combat
Simulator* (2nd Edition, 1983) rules — the tabletop game, not a re-skin of a video game. Fly a
Federation, Klingon, Romulan, Gorn, or Orion vessel against an AI opponent (or, someday, another player) using
the same power-allocation, firing-arc, and damage-location mechanics as the original board game.

It's a single self-contained HTML file. No install, no server, no external assets — open it in a
browser and play. Every ship sprite, sound effect, and UI element is embedded directly in the
file.

## How to play

Open `StarTrek_TacticalCommand_GAME.html` in any modern browser (Chrome, Firefox, Safari, Edge —
desktop or mobile). There's nothing to install and nothing to configure to get started.

1. **Pick your side** — Federation, Klingon, Romulan, Gorn, or Orion — and a ship from that faction's roster.
   Both your ship and the enemy's show a live artwork preview as you browse the dropdown.
2. **Pick a difficulty** — six tiers, Cadet through Legend (see below).
3. **Power Allocation Phase** — split your ship's total power across Movement, Shields, and
   Weapons (and Cloak, if your ship has one). This is the strategic heart of the game: overcommit
   to weapons and you're an easy target; overcommit to shields and you can't hurt anything.
4. **Tactical Advantage** — whoever allocated *less* movement power moves last each turn, seeing
   the other side's position first. Ties are broken by a die roll.
5. **Three Sensors → Movement → Firing sub-phases per turn** — maneuver into arc, try to lock
   sensors on the enemy (or scan for a cloaked one), and fire when you've got a shot.
6. **Repeat until one side's superstructure hits zero**, or you disengage.

The combat log panel on the left can be resized by dragging the handle on its right edge, and its
text size is controlled separately by the "UI Scale" +/− control at the top-center of the
tactical map (70%-160%) — the two work together if the default is too cramped to read comfortably.
That same control bar also holds "Recenter," which frames both ships back in view if you've
scrolled or zoomed away from the action.

Combat logs can be exported from the victory/defeat screen — useful for reviewing a fight, or (see
below) for teaching the AI.

## Rules fidelity

This isn't a loose interpretation — power costs, firing charts, damage-location tables, shield
mechanics, and the cloak-detection rules are all pulled directly from the FASA rulebook and the
three Recognition Manual sourcebooks (Federation, Klingon, Romulan) included in this project.
Gorn and Orion ships come from a fourth source in the same project — the general Starship Combat
rules data, which documents both factions' hulls even though neither gets its own dedicated
Recognition Manual here. Where a mechanic's source is ambiguous or two books disagree, the
project's house rule is **Recognition Manuals win** over the Construction Manual.

Two rule-complexity tiers are available in Setup:
- **Basic** — a cloaked ship simply can't be fired on until it decloaks.
- **Intermediate** — the fuller sensor-lock and cloak-detection game: scan a shield arc, roll
  against the Cloak Detection Table (range- and movement-dependent), and a successful detection
  gives your side a firing solution — with a to-hit penalty — until the lock breaks.

**One deliberate departure from the source material, in progress:** a self-destruct/surrender
system is being built on top of the real FASA rules for ship explosions and blast damage. Most of
it is sourced straight from the book — but the Klingon behavior isn't. The rulebook actually
describes Klingons as *reluctant* to self-destruct (it risks dishonor to their family line) and
says nothing at all about whether they'd ever surrender. This project has chosen, deliberately, to
go further than the 1983 source material does: **Klingons in this game never surrender and never
accept a surrender offer — they fight to actual destruction, full stop ("Death First").** Provoking
one with a surrender offer they'll never accept isn't free, either — expect a real, mechanical
consequence, not just a rejected offer. None of this is FASA canon; it's this project's own
informed extrapolation, built because decades of on-screen Klingon culture have been established
since that rulebook was written. If you're comparing this game against the original tabletop rules,
this is the one place to expect a genuine divergence, not a bug.

## The fleet

**Federation** — Constitution (3 marks), Enterprise refit (3 marks), Federation II "Dreadnought"
(2 marks, triple-nacelle design), Chandley Class frigate (3 marks), Excelsior Class battleship
(2 marks — the largest and most heavily-armed Federation hull in the fleet, "The Great
Experiment," fitted with a classified TransWarp drive per the sourcebook's own notes).

**Klingon** — D-7 Battle Cruiser (6 marks: A/C/G on the classic hull, M/R/S on a distinct
hybrid-tech hull reflecting a Klingon-Romulan technology exchange — R and S are the marks that
carry a cloaking device), K-22 Bird of Prey (small scout), D-32 Stronger Bird (mid-size cruiser),
L-42 Great Bird (large frigate), D-2 Stingtongue (destroyer, missile-heavy), T-5 Throne Seeker
(assault ship), L-24 Ever-Victorious (battleship — the largest Klingon hull in the fleet), D-18
Gull (cloak-capable destroyer), L-9 Saber (frigate). 14 Klingon hulls in total.

The two D-7 hulls aren't just a visual choice — they line up with real in-universe dates derived
from this project's own FASA stardate research. The classic hull (A/C/G) spans roughly 2186-2210,
a generation before Kirk's five-year mission through the TOS/TAS window itself; the hybrid hull
(M/R/S) picks up right after and runs through 2219, past *The Motion Picture*'s 2217. It's a nice
coincidence that the cloak-bearing marks (R, S) also turned out to be the chronologically latest —
that wasn't planned when the hulls were split, it just checked out later.

**Romulan** — V-8 Bird of Prey "RIS Talon" (2 marks, cloak-capable), V-30 Winged Defender (2
marks, heavy cruiser), V-11 Stormbird (3 types — Type 1 is documented in the sourcebook as
literally flying on Klingon-built engines, a real in-canon precursor to the Klingon tech-exchange
lore above).

**Gorn Alliance** — SS-3 Destroyer, MA-12 Cruiser, BH-2 Battleship.

**Orion Colonies** — Wanderer and Lightning, both Blockade Runners. Small, fast, and armed —
these aren't unarmed traders. Lightning in particular is built for speed over firepower.

Every ship's stats are sourced from the FASA Recognition Manuals, not invented — where a stat
block's provenance is unusual (an image transcription rather than a project source file, for
instance), it's noted honestly in `HANDOVER.md` rather than presented as more verified than it is.
A handful of fields (mostly `moveRatio`) were left blank in the sourcebook for the Gorn and Orion
ships specifically — those are reasoned estimates, flagged as such in `HANDOVER.md`, not sourced
numbers.

## Ship Recognition Database

A browsable in-game reference of every ship documented in the source material — not just the ones
you can fly. Filter by faction, search by name, and hover any entry for a quick preview with
artwork and stats before clicking through to the full dossier. Ships that are fully built and
playable show their real in-game art; ships that are documented in the sourcebooks but not yet
built into the game show a generic silhouette instead, so you can always tell the difference at a
glance.

## AI difficulty

Six tiers, selected on a slider in Setup: **Cadet → Ensign → Lt. Cmdr → Captain → Admiral →
Legend.**

The first five are hand-tuned heuristics of increasing sophistication (range-awareness, cloak
usage, shield-facing optimization). **Legend is different in kind, not just degree**: it's built
directly from the *user's own* combat logs — a human+AI read-and-patch process, not machine
learning. Every behavior it carries was identified as a pattern that repeated across multiple
different games (not a one-off), and every branch of code is commented with which log it came
from. If a battle report reveals a new consistent tendency, it can be added the same way. Legend
currently reflects: a patient, fully-committed cloak approach that holds until point-blank range;
an all-or-nothing alpha strike the instant it decloaks; a willingness to take low-probability shots
rather than wait for a perfect one; and prioritizing repositioning over weapons power when hunting
a cloaked target.

## What's not finished yet

- Self-destruct and surrender (see "Rules fidelity" above for the Klingon house-rule note) — the
  underlying blast-damage math is built and tested, but there's no button or AI decision logic yet.
  Nothing changes in actual gameplay until this ships.
- A Klingon emblem treatment for the UI is in design (see `HANDOVER.md` for the in-progress
  options) — nothing from that work is in this build yet.
- The Excelsior (Federation battleship) is fully statted in the sourcebook data but not yet built
  into the game.
- A full ship-construction ("shipyard") mode is staged separately and not yet wired in.

## Project files

- `StarTrek_TacticalCommand_GAME.html` — the game. The only file you need to play.
- `romulan_emblem_studio.html` — a separate, standalone tool for live-tweaking a Romulan crest
  design (colors, twin-globe placement). Not part of the game; a design sandbox.
- `HANDOVER.md` — a detailed technical log for continuing development, written for whoever (or
  whatever) works on this next.
- `README.md` — this file.

---
*Star Trek and all related marks are trademarks of Paramount. This is a private, non-commercial
fan project built for personal tabletop-adjacent play — it is not distributed or sold.*
