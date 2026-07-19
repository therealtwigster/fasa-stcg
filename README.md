# Star Trek: Tactical Command Simulator

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

**3. Controls**
- **Click a hex** to move there; **arrow keys / A-D / Q-E** rotate facing.
- **Scroll** to zoom the tactical map; drag to pan.
- Weapons fire within their **firing arcs** (six 60° arcs around the ship). Range affects hit chance and damage per the FASA firing charts.
- Cloak-capable ships (Romulan Bird of Prey, late-mark Klingon D-7) can spend power to cloak.

The game ends when a ship is destroyed, or when engine damage drops a ship's power to zero (triggering a capture/surrender outcome).

---

## Playable ship roster

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

### Klingon
| Ship | Power | Move | Shield Ratio | Max Shield/Face | Superstructure | Cloak |
|------|-------|------|--------------|-----------------|----------------|-------|
| D-7 A (VIII) | 40 | 4 | 1.0 | 8 | 20 | — |
| D-7 C (VII) | 32 | 4 | 1.0 | 9 | 18 | — |
| D-7 G (VIII) | 40 | 4 | 1.0 | 8 | 20 | — |
| D-7 M (IX) | 44 | 3 | 0.5 | 12 | 20 | — |
| D-7 R (IX) | 44 | 3 | 0.5 | 12 | 20 | Yes |
| D-7 S (IX) | 44 | 3 | 0.5 | 12 | 22 | Yes |

### Romulan
| Ship | Power | Move | Shield Ratio | Max Shield/Face | Superstructure | Cloak |
|------|-------|------|--------------|-----------------|----------------|-------|
| V-8 Bird of Prey Type 1 | 26 | 3 | 0.5 | 8 | 15 | Yes |
| V-8 Bird of Prey Type 4 | 28 | 3 | 0.5 | 11 | 15 | Yes |

The **Constitution** and the movie-era **Enterprise refit** are treated as distinct FASA hulls (both Class XI cruisers), each with its own sprite.

---

## Ship Recognition Database

Click **◈ Ship Recognition Database** on the scenario screen to open an in-game fleet reference, styled as a starfleet intel file:

- **Left roster** — filter by faction, search by name, grouped by faction and role.
- **Right dossier** — targeting-reticle silhouette, FASA reliability-grade stamp, variant selector, full stat grid, weapons table with a six-segment firing-arc indicator, and combat-efficiency bars.
- **Live sprites** for the four playable hulls (Constitution, Enterprise refit, D-7); procedural silhouettes for the rest.
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

## Credits & intellectual property

This is a fan-made tactical simulator built on the tabletop rules and ship data from FASA's *Star Trek: Starship Tactical Combat Simulator* and its ship-recognition manuals. Star Trek and all related marks are the property of their respective rights holders. This project is non-commercial and intended for personal, educational use.
