# Star Trek: Tactical Command Simulator

> **Build v1.33-S44** · single-file, no dependencies

A browser-based tactical starship combat game built on the **FASA Star Trek: Starship Tactical Combat Simulator** rules. Command a capital ship on a hex grid, divide power between engines, shields, and weapons across a multi-phase turn, and fight a difficulty-scaled AI to destruction or a power-out surrender.

Everything — code, art, ship data, and the fleet database — lives in **one HTML file** with no external assets, server, or internet connection. Just open it in a browser.

---

## Running the game

Open `StarTrek_TacticalCommand_GAME.html` in any modern desktop browser (Chrome, Firefox, Edge, Safari). No install, build step, or network needed. To confirm your version, check the build stamp in the header (**v1.33-S44**) or the top line of any exported combat log.

---

## How to play

### 1. Set up the battle
- **Play As** — Federation, Klingon, or Romulan (sets your faction theme and sides).
- **Your Ship / Enemy Ship** — pick any playable variant from the roster below.
- **AI Difficulty** — Cadet → Ensign → Lt. Cmdr → Captain → Admiral. These are genuinely different AI behaviors, not just stat tweaks (see **Difficulty** below).
- **◈ Ship Recognition Database** — browse the full fleet visually and pick your hull.
- **⬡ Engage** — start.

### 2. Each turn follows FASA's phase sequence
1. **Power Allocation** — split your reactor output between movement, shields (per facing), and arming weapons. Commit when ready.
2. **Tactical Advantage** — a contested roll; the loser must move first each sub-phase (exposing their position before the winner commits).
3. **Movement / Firing ×3** — three interleaved movement and firing sub-phases.
4. **Repower Shields** — shields recharge, and the next turn begins.

### 3. Winning
Destroy the enemy's superstructure, or knock out its power entirely (a **power-out**, which triggers a boarding/capture narrative). The end screen gives a written after-action account and full shot statistics.

---

## Controls

**Movement (during a movement phase)**
- **↑ / W** — advance one hex forward · **↓ / S** — reverse
- **← / A** — rotate to port · **→ / D** — rotate to starboard
- **Click a highlighted green hex** — move there directly
- **Hold / Undo** buttons — burn a move point in place, or take back a move

**View**
- **Left-drag** — pan · **Scroll** — zoom to cursor · **Double-click** — reset view · **F** — focus/center on your ship

**Firing (during a firing phase)**
- Click individual weapon buttons, or **Fire All**. Each shot rolls to-hit against the FASA firing chart for that weapon at the current range.

**End screen**
- **⬇ Download Combat Log** — save the full battle log as a text file
- **Space** — start a new mission (mouse clicks won't restart, so you can freely copy the log/narrative)

---

## The cloak system (fog of war)

Cloak-capable ships (Klingon Birds of Prey, Romulan warbirds, some D-7 variants) can cloak during power allocation. Cloaking costs power and takes weapons offline for the turn — but it makes the ship **genuinely hidden**, not just dimmed:

- **A cloaked enemy vanishes from the map.** In its place, a pulsing **◇ LAST KNOWN** marker sits at the last hex you actually saw it. It freezes there while the ship moves unseen — hover it for a readout of when contact was lost.
- **Firing at a cloak is a guess.** Your to-hit is slashed (you'll see *"firing solution reduced to a guess"* and mostly miss), and your shots trace toward the last-known position, not the real one.
- **The enemy readout obfuscates.** By default the Enemy Contact panel shows **◇ SENSOR CONTACT LOST** while the target is cloaked. A toggle in the panel header switches it to **Last Known** — frozen, greyed-out stats stamped with the turn you last saw them.
- **Difficulty gates your intel.** At lower difficulty you get sensor hints (a shimmer over the ship's true hex, an impact flash when a blind shot lands). At **Admiral you get nothing** — total fog.
- **The AI plays by the same rules.** Cloak *your* ship and the AI loses your position too, navigating and shooting at where it last saw you. No cheating.

The counter-play: a cloaked ship can't fire. Watch for it to **decloak and strike**, and punish the moment it reappears.

---

## Difficulty tiers

The five levels are distinct AI code paths. Higher tiers unlock more of the AI's behavior — if you only play Ensign, you're seeing a fraction of what the opponent can do.

| Tier | Behavior |
|------|----------|
| **Cadet** | Random power, fires ~60% of the time regardless, no cloak, wanders. A practice dummy. |
| **Ensign** | Fixed power split, fires when a weapon bears, cloaks only to survive when hurt, closes then holds. |
| **Lt. Cmdr** | Range-aware power, disciplined fire, uses cloak to disengage and to approach hidden. |
| **Captain** | Optimized power scaled to range, concentrates shields toward you, jinks to spoil your aim. |
| **Admiral** | Full optimization — commits to cloaked approaches, turns aggressive when you're weak, decloaks and strikes at point-blank, and gives you zero sensor hints. |

---

## Combat log

Every battle records a full turn-by-turn log — power splits, tactical-advantage rolls, every shot's chart/range/roll/result, damage and system hits, and cloak state. At the end screen, **Download Combat Log** saves it as a text file (stamped with the build number). It's great for reviewing a fight, sharing a war story, or reporting a bug.

---

## Ship roster

All stats and weapon arcs are transcribed from the FASA ship recognition manuals. Weapon firing arcs follow the manual's forward/aft-quarter notation (a "forward-port" weapon fires forward **and** to port).

**Federation** — Constitution (base) and Constitution Mk I/II/III; Enterprise Mk I/II/III; Federation-class Mk I/II.

**Klingon** — D-7 (base) and D-7 A/C/G/M/R/S variants; D-4 Predator; D-2 Sting Tongue; D-18 Gull; L-9 Saber; T-5 Throne Seeker; L-24 Ever Victorious; **K-22 Bird of Prey** (cloak scout); D-32 Stronger Bird (cloak); L-42 Great Bird (cloak).

**Romulan** — V-8 Bird of Prey (base) and Type 1/Type 4; V-30 Winged Defender Type 1/Type 2. (Romulan cloaking hulls.)

> **A note on Birds of Prey:** the light cloak scouts (K-22, V-8) are deliberately fragile and short-ranged. One-on-one against a cruiser they should lose — in the source material they hunt in **groups**. Fleet combat (multiple ships per side) is a planned feature that will let them fight the way they're meant to.

---

## Ship Recognition Database

The **◈ Ship Recognition Database** on the scenario screen is a browsable fleet reference — hull art, class silhouettes, and stat blocks for the ships in the game. Use it to pick your ship visually or just to browse the fleets.

---

## Credits & intellectual property

This is a personal, non-commercial fan project built on the tabletop rules of the FASA *Star Trek: Starship Tactical Combat Simulator*. *Star Trek* and all related marks are the property of their respective rights holders. All in-game audio is original synthesis; no copyrighted sound recordings are included.
