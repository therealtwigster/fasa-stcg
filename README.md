# Star Trek: Tactical Command

A single-file browser implementation of the FASA Starship Tactical Combat Simulator. No installation, no server, no dependencies — open the HTML file and play.

---

## Quick Start

1. Open `StarTrek_TacticalCommand_GAME.html` in any modern browser (Chrome, Firefox, Edge, Safari)
2. Choose your faction — **Federation** or **Klingon Empire**
3. Set the AI difficulty (1 = Cadet, 5 = Admiral)
4. Click **Launch Mission**

That's it. The game runs entirely in your browser.

---

## The Interface

The game has four tabs across the top:

| Tab | What it's for |
|-----|---------------|
| **Tactical Map** | The hex grid where combat takes place. Combat log is on the left panel. |
| **Power Allocation** | Set your power budget each turn before moving or firing. |
| **Damage Control** | Real-time ship silhouette showing hull integrity and shield status. |

The **status bar** below the tabs shows the current turn, current phase, and your ship's remaining hull percentage at all times.

---

## How a Turn Works

Every turn follows the FASA sequence exactly:

```
1. Power Allocation
2. Tactical Advantage
3. Move Phase 1  →  Fire Phase 1
4. Move Phase 2  →  Fire Phase 2
5. Move Phase 3  →  Fire Phase 3
6. Repower
```

You and the AI execute each phase simultaneously. Movement and fire declarations are revealed at the same time.

---

## Phase by Phase

### Power Allocation

Go to the **Power Allocation tab** at the start of each turn.

- **Power to Movement** — slider sets how many power units go to engines. More power = more hexes moved per phase.
- **Power to Shields** — slider sets total shield power. Distributed across all 6 shield faces.
  - Click **MANUAL** next to the shields header to allocate per-face. Six individual sliders appear, one per shield face. Click **AUTO** to return to even distribution.
- **Weapon power** — arm each weapon using its arm button, then set power for beam weapons using the number input. Inputs are hard-capped to the remaining budget — you cannot overspend.
- Click **Commit Power** when done. You cannot change allocations after committing.

The budget bar at the top of the power tab shows how much of your total power is used. It turns gold when fully allocated.

### Movement Phases

During Move 1, Move 2, and Move 3:

- **Click a green hex** to move your ship there. Reachable hexes are highlighted green.
- Green hex cost is shown as a number in each hex based on terrain.
- You can rotate before or after moving.
- Click **Undo Last Move** to take back your last move within the current sub-phase.
- Click **Hold Station** to stay in place (still uses a movement action).
- Click **End Phase** when done moving.

**Keyboard controls during movement:**

| Key | Action |
|-----|--------|
| `↑` or `W` | Move forward one hex |
| `Q` | Rotate 60° port (counter-clockwise) |
| `E` | Rotate 60° starboard (clockwise) |
| `A` | Sideslip port |
| `D` | Sideslip starboard |

> The tactical map must have focus for keyboard controls to work. Click anywhere on the map hex grid first.

### Fire Phases

During Fire 1, Fire 2, and Fire 3 your armed weapons appear as individual buttons in the right sidebar.

- **Glowing red button** = weapon is charged and ready to fire. Click it to fire.
- **Amber button with reason text** = weapon is blocked. The reason is shown directly on the button:
  - `OUT OF RANGE — 12 hexes (max 8)` — close the distance
  - `NO POWER ALLOCATED` — go back to Power Allocation next turn
  - `NOT IN ARC — rotate to: F/F-Stbd` — rotate your ship to bring target into arc
  - `NEBULA — SENSORS DEGRADED` — you are in a nebula, accuracy reduced
- **No Fire** — skip this fire phase without firing any weapons
- **End Phase** — advance to the next phase (unfired weapons are skipped)

You can fire weapons in any order across the three fire phases. A weapon can only fire once per turn.

**Terrain badges** on weapon buttons warn you when terrain is affecting the engagement:

| Badge | Meaning |
|-------|---------|
| `⚠ IN NEBULA` | Your ship is in a nebula — sensor lock degraded |
| `⚠ IN ASTEROID` | Your ship is in an asteroid field — move costs increased |
| `⚠ TGT NEBULA` | Target is in a nebula — accuracy penalty applies |
| `⚠ TGT ASTEROID` | Target is in asteroids — beam weapons partially deflected |

### Repower Phase

At the end of each turn, power is automatically restored. All weapon charges reset. The turn counter advances and you return to Power Allocation.

---

## Weapons

### Beam Weapons (Phasers / Disruptors / Blasters)

- Arm the weapon using the arm button in the Power Allocation tab
- Set power using the number input (0 to weapon maximum)
- Damage equals the power you put in, plus range bonuses at close range
- Can fire in any fire phase

### Missile Weapons (Photon Torpedoes / Plasma)

- Arm the weapon using the arm button — this reserves the arm cost from your power budget
- No additional power input needed
- Fixed damage regardless of range
- Romulan plasma weapons deal degrading damage the further the target is

### Accelerator Cannons (Orion)

- Treated as missiles — fixed arm cost, fixed damage

---

## Terrain

| Hex colour | Terrain | Effect |
|------------|---------|--------|
| Dark blue | Open space | No modifier. Stars visible inside hex. |
| Purple | Nebula | Sensors degraded. No sensor lock. Beam accuracy reduced. |
| Orange | Asteroid field | +1 movement cost per hex. +1 cover vs beam weapons. |
| Green | Gravity well | +1 movement cost to exit. Torpedo trajectories arc. |

---

## Damage

When a weapon hits, the game resolves:

1. **Which shield face** was hit (based on firing geometry)
2. **Shield absorption** — shield points absorb damage first
3. **Penetrating damage** — remainder hits the ship
4. **Damage location** (d10 roll):

| Roll | Location |
|------|----------|
| 1 | Shield Generator |
| 2 | Beam Weapon |
| 3 | Missile Weapon |
| 4–6 | Engine |
| 7–9 | Superstructure |
| 10 | Sensors |

Check the **Damage Control tab** to see your current ship state. Shield faces with destroyed generators show a red X. The superstructure box track at the bottom shows remaining hull — green above 50%, amber between 25–50%, red below 25%.

---

## Combat Log

The combat log is the left panel on the Tactical Map tab. It shows every dice roll, chart lookup, hit/miss result, damage location, and system status message in real time. New entries appear at the top.

---

## Ship Roster (v1)

| Ship | Faction | Power | Move Ratio | Superstructure |
|------|---------|-------|-----------|---------------|
| Constitution class | Federation | 38 | 4/1 | 24 |
| D-7 class | Klingon Empire | 34 | 4/1 | 20 |

Additional ships from the FASA Ship Recognition Manuals will be added in subsequent versions.

---

## AI Difficulty

| Level | Designation | Behaviour |
|-------|-------------|-----------|
| 1 | Cadet | Passive, moves randomly, fires opportunistically |
| 2 | Ensign | Basic positioning, prefers forward arcs |
| 3 | Lieutenant | Closes to optimal range, allocates power intelligently |
| 4 | Commander | Flanks, concentrates fire on weakened shields |
| 5 | Admiral | Full tactical reasoning, exploits terrain, varies timing across fire phases |

---

## Factions

| Faction | Beam Weapon | Missile | Shield Ratio |
|---------|------------|---------|-------------|
| United Federation of Planets | Phaser (Chart W) | Photon Torpedo (Chart O) | 1/2 |
| Klingon Empire | Disruptor (Chart S) | Photon Torpedo (Chart O) | 1/2 |

Romulan, Orion, and Gorn factions are data-complete and will become selectable in a future version.

---

## Tips

- **Power is always a trade-off.** Moving fast means weaker shields. Heavy shields means less weapon power. You cannot max everything.
- **Firing arcs matter more than range.** A weapon with a narrow forward arc is useless if the enemy is on your aft quarter. Rotate before committing to a fire phase.
- **Shield generators can be destroyed.** Once gone, that face has zero shielding for the rest of the game. Protect damaged faces by rotating them away from the enemy.
- **Nebulas are double-edged.** Moving into one hides you from precise sensor lock but also degrades your own weapons.
- **The undo button is your friend.** You can take back moves within a sub-phase. Use it to explore positioning before committing.
- **Manual shield allocation** lets you stack points forward when closing on an enemy, or rear-weight shields when breaking off. Switching back to AUTO resets all faces to even distribution.

---

## Technical Notes

- Single HTML file — no server, no build step, no CDN dependencies
- All audio is procedurally synthesised via the Web Audio API (no audio files)
- Runs in any modern browser; tested in Chrome 120+, Firefox 121+, Safari 17+
- Save state is not implemented in v1 — each session is a fresh game
- File size: approximately 190KB

---

## Based On

FASA Starship Tactical Combat Simulator (FASA 2003, 2nd Edition)  
Ship Construction Manual 2nd Edition (FASA 2204)  

Game mechanics implemented under the principle that rules systems and statistical data are not copyrightable. All code, artwork, and ship renderings are original. Star Trek is a trademark of Paramount Global.
