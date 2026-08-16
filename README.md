# Star Trek: Tactical Command Simulator

> **Build v1.23-S34** · 2026-08-15 18:08 UTC


A single-file, browser-based tactical starship combat game built on the **FASA Star Trek: Starship Tactical Combat Simulator** rules. Command a capital ship on a hex grid, manage power between engines, shields, and weapons across a multi-phase turn, and fight an AI opponent to destruction or surrender.

Everything — code, art, ship data, and the fleet database — lives in one HTML file with no external dependencies. Just open it in a browser.

---

## Running the game

Open `StarTrek_TacticalCommand_GAME.html` in any modern desktop browser (Chrome, Firefox, Edge, Safari). No server, build step, or internet connection is required.

---

## How to play

**1. Set up the battle (scenario screen)**
- **Play As** — choose Federation, Klingon, or Romulan.
- **Your Ship / Enemy Ship** — pick from every playable variant (see roster below).
- **AI Difficulty** — Cadet through Admiral (5 levels).
- **◈ Ship Recognition Database** — opens the full fleet database to browse hulls and pick your ship visually (see below).
- **⬡ Engage** — start the battle.

**2. Each turn runs through FASA's phase sequence**
1. **Power Allocation** — divide your ship's power pool between movement, shields (per face), and arming weapons. Commit when ready.
2. **Tactical Advantage** — a contested roll; the loser must move first each sub-phase.
3. **Movement / Firing** ×3 — three interleaved movement and firing sub-phases per turn.
4. **Repower Shields** — end-of-turn shield regeneration.

**3. Play the battle**
- Move, rotate, and fire through each phase. Full controls, display legends, and firing options are in the **Interface, controls & displays** section below.
- Weapons fire within their **firing arcs** (six 60° arcs). Range affects hit chance and damage per the FASA firing charts.
- Cloak-capable ships (Romulan Bird of Prey, late-mark Klingon D-7) can spend power to cloak.

The game ends when a ship is destroyed, or when engine damage drops a ship's power to zero (triggering a capture/surrender outcome).

---

## Interface, controls & displays

The screen is divided into three areas: the **tactical map** (center), the **right sidebar** (your ship's status and weapon controls), and the **combat log** (bottom). Below is what each element shows and how to use it.

### The tactical map

The hex grid where the battle plays out. Your ship and the enemy are drawn as top-down silhouettes (real counter art where available, otherwise a faction-styled procedural hull).

- **Heading arrow** — a bright arrowhead on each ship points in its current facing (forward).
- **Hex-edge shields** — six colored segments trace the hex edges around each ship, one per shield facing. **Green** = charged and in good order (brighter/thicker = stronger); a **thin white line** = the generator works but that face is uncharged; **red with an ✕** = that shield generator is destroyed. The forward face always sits on the ship's heading side, so you can read at a glance which arcs are protected.
- **Range rings** — during a firing phase, dashed blue rings radiate from your ship, one for each distinct weapon max-range, labeled in hexes. Use them to judge whether the enemy is inside a given weapon's reach before committing power.
- **Terrain** — asteroid fields show miniaturized rock art (each hex varied); nebulae appear as dim purple hexes (they scatter sensors); gravity wells are faint green. Terrain is randomized every game.
- **Firing-arc overlay** — when you have a weapon selected/armed, the target's arc is highlighted green (in-arc) or red (out-of-arc).

**Map controls:**
- **Left-click a hex** — move your ship there (during a movement phase).
- **Left-click-drag** — pan the map around.
- **Scroll wheel** — zoom in and out.
- **⊕ Recenter button** (top-right of the map) — reframe both ships in view.
- **Double-click** — reset the view.
- **Arrow keys**, or **A/D**, or **Q/E** — rotate your ship's facing.

### The right sidebar

Tabs across the top switch between **◈ Power Allocation** and the weapon firing view.

- **Pinned stats bar** — always visible at the top of the sidebar: **HULL** (superstructure current/max), **PWR** (power current/total), and six shield facings (F, FS, AS, A, AP, FP) color-coded by strength (✕ for a destroyed generator).
- **Ship cards** — "Your Ship" and "Enemy Contact" panels show hull, shields, and power bars. **Hover any bar** for a styled tooltip with exact current/max values (superstructure boxes, total shields across active facings, reactor output), for both your ship and the enemy.
- **Power Allocation tab** — divide your power pool between movement, shields (per face), and arming weapons. Each weapon has a **power slider** (green→amber→red track) with a live value/max readout. Selecting a beam auto-assigns 1 point; drag a beam to zero to un-select it. Systems that are **knocked out** (a destroyed weapon mount or shield generator) are flagged in red — "⊘ KNOCKED OUT" / "⊘ GENERATOR KNOCKED OUT" — so you know why you can't power them. Commit when ready.
- **Weapon firing view** — each weapon is a compact row: a small **FIRE** button (color-coded — green when ready and in range, amber when blocked, faded once fired) with a status glyph and the weapon's name, and for beams a separate **⊕ PAIR** button. **Hover the FIRE button** for a tooltip with the full detail: status, in-range/out-of-range, firing arcs, damage, and power.

### Firing weapons

Three ways to fire:
- **Single** — click a ready weapon's **FIRE** button to fire it on its own.
- **Fire a pair** — click the **⊕ PAIR** button on two ready beam banks (each turns to **✓** and highlights), then **▶▶ FIRE SELECTED PAIR** at the top of the panel fires both together. Good for concentrating two phaser banks on one facing.
- **Fire all** — **⚡ FIRE ALL READY WEAPONS** looses every ready weapon in a staggered rolling volley. Each weapon still rolls its own to-hit and damage.

**Weapon effects by faction/era:** Federation TOS-design phasers (FL-series, FH-6 and below) fire a **solid blue beam** that brightens with the power you allocate; movie-era phasers (FH-7+, e.g. Enterprise refit, Federation II dreadnought) fire **gold rapid-fire pulses** (more power = more pulses). Each bank fires from its own point on the hull. Klingon/Romulan disruptors are procedural beams, and the Romulan **plasma torpedo** is a slow orange fireball that dims and cools as it crosses each hex — mirroring plasma's damage falloff with range. Projectiles resolve their hit exactly when they reach the target.

**Sensor damage:** if your sensors are hit, the enemy contact on the map gets visual static and an uncertainty ring — degraded targeting resolution scales with the damage.

### The combat log

Runs along the bottom, **oldest at top, newest at the bottom**, and auto-scrolls so the latest result is always in view. It reports movement, to-hit rolls, damage by shield facing, critical hits, and kill narratives (Federation ships fire "phasers," Klingon/Romulan "disruptors").



Every variant below is fully playable, with stats and weapons derived directly from the FASA ship-recognition manuals.

### Federation
| Ship | Power | Move | Shield Ratio | Max Shield/Face | Superstructure |
|------|-------|------|--------------|-----------------|----------------|
| Constitution Mk I | 36 | 4 | 1.0 | 9 | 20 |
| Constitution Mk II | 44 | 4 | 0.5 | 16 | 20 |
| Constitution Mk III | 48 | 4 | 0.33 | 16 | 22 |
| Enterprise (refit) Mk I | 60 | 4 | 0.25 | 16 | 26 |
| Enterprise (refit) Mk II | 64 | 4 | 0.25 | 16 | 27 |
| Enterprise (refit) Mk III | 68 | 4 | 0.25 | 16 | 28 |
| Federation II Dreadnought Mk I | 82 | 6 | 0.25 | 15 | 62 |
| Federation II Dreadnought Mk II | 86 | 6 | 0.25 | 20 | 62 |
| Chandley Mk I (XI) | 48 | 3 | 0.33 | 16 | 22 |
| Chandley Mk II (XI) | 52 | 3 | 0.33 | 16 | 22 |
| Chandley Mk III (XI) | 56 | 3 | 0.25 | 16 | 22 |

### Klingon
| Ship | Power | Move | Shield Ratio | Max Shield/Face | Superstructure | Cloak |
|------|-------|------|--------------|-----------------|----------------|-------|
| D-7 A (VIII) | 40 | 4 | 1.0 | 8 | 20 | — |
| D-7 C (VII) | 32 | 4 | 1.0 | 9 | 18 | — |
| D-7 G (VIII) | 40 | 4 | 1.0 | 8 | 20 | — |
| D-7 M (IX) | 44 | 3 | 0.5 | 12 | 20 | — |
| D-7 R (IX) | 44 | 3 | 0.5 | 12 | 20 | Yes |
| D-7 S (IX) | 44 | 3 | 0.5 | 12 | 22 | Yes |
| K-22 Bird of Prey (V Scout) | 25 | 2 | 1.0 | 10 | 9 | Yes |
| D-32 Stronger Bird (VII Cruiser) | 46 | 4 | 0.5 | 10 | 15 | Yes |
| L-42 Great Bird (IX–X Frigate) | 55 | 3 | 0.33 | 15 | 18 | Yes |

### Romulan
| Ship | Power | Move | Shield Ratio | Max Shield/Face | Superstructure | Cloak |
|------|-------|------|--------------|-----------------|----------------|-------|
| V-8 Bird of Prey Type 1 | 26 | 3 | 0.5 | 8 | 15 | Yes |
| V-8 Bird of Prey Type 4 | 28 | 3 | 0.5 | 11 | 15 | Yes |
| V-30 Winged Defender Type 1 (XII) | 68 | 4 | 0.33 | 13 | 30 | Yes |
| V-30 Winged Defender Type 2 (XII) | 68 | 4 | 0.33 | 13 | 31 | Yes |

The **Constitution** and the movie-era **Enterprise refit** are treated as distinct FASA hulls (both Class XI cruisers), each with its own sprite.

---

## Ship Recognition Database

Click **◈ Ship Recognition Database** on the scenario screen to open an in-game fleet reference, styled as a starfleet intel file:

- **Left roster** — filter by faction, search by name, grouped by faction and role.
- **Right dossier** — targeting-reticle silhouette, FASA reliability-grade stamp, variant selector, full stat grid, weapons table with a six-segment firing-arc indicator, and combat-efficiency bars.
- **Live sprites** for hulls that have scanned counter art (Constitution, Enterprise refit, D-7, Romulan V-8 Bird of Prey, V-30 Winged Defender, Chandley); procedural silhouettes for the rest.
- The canonical reference mark for each ship is marked with a glowing gold ★.

Selecting a playable ship and variant sets it as your ship and returns you to the scenario screen, ready to Engage. The database also catalogs dozens of non-playable reference hulls from the Federation, Klingon, and Romulan manuals for browsing.

---

## Factions

| Faction | Signature ship | Style |
|---------|----------------|-------|
| **Federation** | Constitution / Enterprise refit | Balanced cruisers, strong phasers and photon torpedoes |
| **Klingon** | D-7 | Aggressive disruptor boats; late marks add cloaks |
| **Romulan** | V-8 Bird of Prey | Cloak-and-strike with devastating plasma weapons |

---

## Rulesets & Customization

At the scenario screen, a **Customization** panel lets you choose how faithful the simulation runs. It's driven by a house-rules registry, so options can grow over time.

**Ruleset — Basic Course vs. Intermediate:**

- **Basic Course** (default) is fast play. Both ships are in permanent sensor contact — you know each other's position, heading and speed, and you fire freely. Cloak uses a simplified homebrew model (a cloaked ship simply can't be fired on).
- **Intermediate** adds the full FASA sensor layer. Each turn now runs a **Sensors Phase before each of the three movement cycles** (`Power → Tac Adv → Scan 1 → Move 1 → Fire 1 → Scan 2 → …`).

**In the Sensors Phase (Intermediate):**

- **Sensor lock** — against a visible enemy, click **Attempt Sensor Lock** (60% base; roll 6 or less on a d10). A lock isn't required to fire — it's intelligence. Once locked, you may ask **one of nine questions** per phase about the target: its available power, how it has prioritized power, shield status by facing, which weapons are armed and with how much power, damage taken, crew status (only if the facing shield is down), and transporter activity. The answers are read from the enemy's real state.
- **Cloak detection** — if the enemy cloaks, its counter vanishes from the map (you'll see only a faint *"contact lost"* ghost at its last-seen hex, and its contact card reads `???`). To fire on it you must first **detect** it: pick one of your **shield arcs** and **Scan**. Detection reads the ion trail, so it's rolled against the **Cloak Detection Table** (range × whether the target moved), is impossible beyond **30 hexes**, and is *harder against a stationary ship* than a moving one. Holding a lock grants **+3** to next phase's detection roll; a hit on you breaks your lock.
- **Firing on a detected cloaked ship** carries a to-hit penalty: **+3** if it was moving, **+5** if it was stationary. The penalty is shown on the weapon's fire tooltip.

The AI plays by the same rules: it rolls its own locks, and against a *cloaked player* it must run detection scans — you'll see its scan sweep arc on the map (green if it found you, cyan if it missed). Its scan **skill scales with difficulty** (Cadet rarely picks the right arc; Admiral almost always does) rather than simply seeing through the cloak.

**Terrain house rules** — **Nebulae** and **Gravity Wells** are each individually toggleable (they're flagged as house rules, since neither is in the FASA core rules) and apply under either ruleset. Asteroid fields and open space are always available.

---

## The battlefield

Each game generates a fresh starfield with randomized terrain — clustered **asteroid fields** (rendered with miniaturized scanned-counter rock art, varied per hex), **nebula patches** (sensor-fouling), and isolated **gravity wells**. Terrain is capped so it never overwhelms the map (at most 50 affected hexes, sometimes none at all), and the ships' start zones are always left clear.

---

## Credits & intellectual property

This is a fan-made tactical simulator built on the tabletop rules and ship data from FASA's *Star Trek: Starship Tactical Combat Simulator* and its ship-recognition manuals. Star Trek and all related marks are the property of their respective rights holders. This project is non-commercial and intended for personal, educational use.
