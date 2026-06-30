# Star Trek: Tactical Command

A single-file browser implementation of the FASA Starship Tactical Combat Simulator. No installation, no server, no dependencies — open the HTML file and play.

---

## Quick Start

1. Open `StarTrek_TacticalCommand_GAME.html` in any modern browser (Chrome, Firefox, Edge, Safari)
2. Choose your faction — **Federation**, **Klingon Empire**, or **Romulan Star Empire**
3. Set the AI difficulty (1 = Cadet, 5 = Admiral)
4. Click **Launch Mission**

That's it. The game runs entirely in your browser. The whole interface re-themes to match your chosen faction's colors — Federation blue, Klingon red-orange, or Romulan green.

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

## Reading the Tactical Map

Every ship on the hex grid shows four small letters around it marking its orientation:

| Letter | Meaning |
|--------|---------|
| **F** | Forward — the direction the bow is pointing |
| **A** | Aft — directly behind the ship |
| **S** | Starboard — to the right of forward |
| **P** | Port — to the left of forward |

A bright arrowhead also points in the Forward direction, color-matched to your faction. Use these together with the firing arc info on each weapon button to judge whether a target is in range and arc before committing power.

### Navigating the Map

| Action | Result |
|--------|--------|
| Scroll wheel | Zoom in/out, anchored to your cursor position (50%–500%) |
| Click your own ship | Centers the view on your ship |
| `F` key | Snap-center the view on your ship |
| Double-click anywhere | Reset zoom to 100% and re-center |
| Click a green hex (move phase) | Move your ship there |

If text or hex details are hard to read at the default zoom, scroll in — the map redraws at any zoom level.

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

Movement happens in **three independent phases** per turn — Move 1, Move 2, Move 3 — not one long move. The move points you committed in Power Allocation are split across the three phases (shown as `Ph.1:2 / Ph.2:1 / Ph.3:1` in the Power tab). **Unused points from one phase do not carry over to the next** — if you don't spend Move 1's points, they're gone when Move 2 starts.

During each move phase:

- **Click a green hex** to move your ship there. Reachable hexes — within *this phase's* remaining points only — are highlighted green.
- Each green hex shows a small number: the movement point cost to enter it (1 for open space, more for difficult terrain).
- A label in the corner of the map shows `Phase 2/3 · 1 pts` so you always know which phase you're in and how many points are left in it.
- The sidebar also breaks down all three phases at once, with the current one marked `▶`.
- You can rotate before or after moving.
- Click **Undo Last Move** to take back your last move within the current phase.
- Click **Hold Station** to stay in place (still uses a movement action).
- Click **End Phase** when done moving — unspent points in this phase are lost.

**Keyboard controls during movement:**

| Key | Action |
|-----|--------|
| `↑` or `W` | Move forward one hex |
| `Q` | Rotate 60° port (counter-clockwise) |
| `E` | Rotate 60° starboard (clockwise) |
| `A` | Sideslip port |
| `D` | Sideslip starboard |
| `F` | Center the view on your ship |

> The tactical map must have focus for keyboard controls to work. Click anywhere on the map hex grid first.

### Fire Phases

Fire 1, Fire 2, and Fire 3 follow each move phase. Your armed weapons appear as individual buttons in the right sidebar, each showing live targeting information:

- **Arc status** — `Arc: F/F-Stbd/F-Port  ✓ TARGET IN ARC` or `✗ NOT IN ARC`, so you know immediately whether the enemy is within this weapon's firing arc.
- **Range status** — `Range: 4 hexes (max 6)  ✓ IN RANGE` or `✗ OUT OF RANGE`.
- **Power/damage** — shows current power committed and expected damage (or `DMG:rng-vary` for plasma weapons, whose damage falls off with range).
- **Glowing button** = weapon is charged and ready to fire. Click it to fire.
- **Blocked button** with a reason — block reasons are now specific and actionable:
  - `OUT OF RANGE — 12 hexes (max 8) — close distance`
  - `NO POWER — set power in Power tab before committing` — power must be committed in the Power tab *before* the fire phase; setting the slider alone isn't enough
  - `NOT IN ARC — covers F/F-Port — rotate ship`
  - `CLOAKED — disengage cloak to fire` (Romulan ships only)
- **No Fire** — skip this fire phase without firing any weapons
- **End Phase** — advance to the next phase (unfired weapons are skipped)

On the tactical map itself, all hexes covered by your armed weapons' firing arcs are tinted teal. The enemy's hex glows bright green when it's a valid target (in arc and in range) or red when it currently isn't.

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

### Missile Weapons (Photon Torpedoes / Plasma Bolts)

- Arm the weapon using the arm button — this reserves the arm cost from your power budget
- No additional power input needed
- Photon torpedoes deal fixed damage regardless of range
- **Plasma bolts (Romulan)** deal degrading damage the further the target is — heaviest near point-blank, falling off sharply at long range. The fire button shows `DMG:rng-vary` instead of a fixed number, and the combat log reports the exact damage rolled for that range each time it fires.

### Accelerator Cannons (Orion)

- Treated as missiles — fixed arm cost, fixed damage

---

## Cloaking (Romulan)

Ships equipped with a cloaking device show an **⬡ ENGAGE CLOAK** button at the bottom of the Power Allocation tab, below the weapons list. This only appears for ships that have the device — Federation and Klingon ships in this version do not.

- Engaging the cloak costs power (shown on the button, e.g. "cost: 15 pwr") and **disarms all weapons** — you cannot fire while cloaked.
- While cloaked your ship renders at low visibility on the tactical map with a `[CLOAKED]` label in place of its name.
- Click **⬡ DISENGAGE CLOAK** to drop the cloak and restore weapons access starting next turn.
- The cloak toggle only works during the Power Allocation phase, before you commit.

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

## Victory and Defeat

When either ship's superstructure reaches zero, the battle ends immediately and a results screen appears with:

- **VICTORY** or **DEFEAT** in large text
- A short narrative paragraph describing how the finishing blow landed — which weapon fired, where it struck, and whether the target's shields had already failed or simply weren't enough. This is generated from what actually happened in that exchange, not a generic message, so a torpedo kill reads differently from a disruptor kill or a plasma bolt kill.
- Turn count and shot accuracy stats for both sides
- A pulsing **"press any key to continue"** prompt — press any key, or click anywhere on the screen other than the New Mission button, to return to the start menu. There's a brief pause before this activates so a key still held down from the heat of combat doesn't skip past the result instantly.

---

## Ship Roster (v1)

| Ship | Faction | Power | Move Ratio | Superstructure |
|------|---------|-------|-----------|---------------|
| Constitution class | Federation | 38 | 4/1 | 24 |
| D-7 class | Klingon Empire | 34 | 4/1 | 20 |
| V-8 Bird of Prey | Romulan Star Empire | 26 | 3/1 | 15 |

The V-8 carries a forward/port/starboard disruptor and a forward-only plasma bolt launcher, plus a cloaking device — see **Cloaking** above. Additional ships from the FASA Ship Recognition Manuals will be added in subsequent versions.

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

| Faction | Beam Weapon | Missile | Shield Ratio | Cloak |
|---------|------------|---------|-------------|-------|
| United Federation of Planets | Phaser (Chart W) | Photon Torpedo (Chart O) | 1/2 | No |
| Klingon Empire | Disruptor (Chart S) | Photon Torpedo (Chart O) | 1/2 | No |
| Romulan Star Empire | Disruptor (Chart J) | Plasma Bolt (Chart M, range-decaying damage) | 1/2 | Yes |

The whole interface re-themes to your chosen faction's color scheme at launch — tabs, the commit button, power bars, weapon-armed indicators, and the header pill all switch from Federation blue to Klingon red-orange or Romulan green automatically.

Orion and Gorn factions are data-complete and will become selectable in a future version.

---

## Tips

- **Power is always a trade-off.** Moving fast means weaker shields. Heavy shields means less weapon power. You cannot max everything.
- **Firing arcs matter more than range.** A weapon with a narrow forward arc is useless if the enemy is on your aft quarter. Rotate before committing to a fire phase.
- **Shield generators can be destroyed.** Once gone, that face has zero shielding for the rest of the game. Protect damaged faces by rotating them away from the enemy.
- **Nebulas are double-edged.** Moving into one hides you from precise sensor lock but also degrades your own weapons.
- **The undo button is your friend.** You can take back moves within a sub-phase. Use it to explore positioning before committing.
- **Manual shield allocation** lets you stack points forward when closing on an enemy, or rear-weight shields when breaking off. Switching back to AUTO resets all faces to even distribution.
- **Cloaking is an all-or-nothing trade.** You can't fire while cloaked, so use it to reposition or break contact, not as a free defense while attacking.
- **Zoom in on tight engagements.** Scroll to zoom and click your own ship to center the view — useful once ships close to short range and the hex grid gets crowded.

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
