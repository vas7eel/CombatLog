# CombatLog

**A BattleTech mod by Vas7eel** · v2.0.0

CombatLog displays a real-time combat log with stats during battles — every hit
with to-hit %, weapons fired, locations destroyed, pilot injuries, ejections, and
mech deaths as they happen. It respects fog of war (damage from unspotted sources
shows as **UNKNOWN**), shows initiative order each round, and tracks per-pilot and
overall lance performance for every mission.

Works with **Vanilla, BTAU (BTA), BEXT (BEX), and RogueTech (RT)**.

## Download

- 📦 **[Download CombatLog.zip](CombatLog.zip)** — then see Installation below
- 🎮 Also on [Nexus Mods](https://www.nexusmods.com/battletech/mods/754)

## Installation

1. Ensure **ModTek** is installed.
2. Extract `CombatLog.zip` and copy the `CombatLog` folder to `BATTLETECH/Mods/CombatLog/`.
3. Launch the game.

## Compatibility

| | |
|---|---|
| BattleTech | 1.9.1 |
| ModTek | 4.2.0+, 4.4.1+, 4.5.0+ |
| HarmonyX | 2.15.0+ |
| BTAU / BEXT / RT | Latest |

## Controls

| Key / Button | Action |
|---|---|
| `L` | Toggle log visibility on/off |
| `K` | Toggle between log and stats view (context-aware on the Argo) |
| Drag title | Move the window |
| ◢ grip | Resize from the bottom-right corner |
| `-` / `+` | Decrease / increase font size |
| `40%` | Cycle background opacity (0–100%) |
| `✕` | Clear the combat log (context-aware) |
| `LOCK` | Lock/unlock auto-scroll to the newest entry |
| `LOG` / `STATS` / `PREFS` / `ARGO` | Switch panels |

## Stats & Awards

Press `K` to switch to the stats panel. The **MISSION** tab shows live totals,
pilot rankings by damage, and award tracking (current leader during combat, winner
at mission end). **Pilot** tabs give per-pilot offense/defense/weapon breakdowns,
attacker breakdown, and nemesis. The **PREFS** tab has in-game toggles and color
configuration, saved automatically to `CombatLog_prefs.json`.

<details>
<summary><strong>Awards</strong></summary>

| | Award | Criteria |
|---|---|---|
| ★ | Top Gun | Most damage dealt |
| ⛊ | Iron Wall | Most damage taken |
| ☠ | Destroyer | Most kills |
| ◎ | Deadeye | Highest hit percentage |
| ♛ | Exhibitionist | Most attacks received |
| ☘ | Can't Touch This | Most potential damage evaded |
| ✚ | It's Just a Flesh Wound | Most injuries suffered |
| ⚔ | Sadist | Most injuries caused |
| ✊ | Rock'em Sock'em | Most melee damage dealt |
| ♨ | Flamin' Hot | Highest peak heat reached |
| ⚠ | This is Fine | Most turns spent overheated |
| ✷ | Purify by Fire | Most heat damage dealt to enemies |
| ☄ | Earthshaker | Most stability damage dealt |
| ⊙ | Headhunter | Killed a mech with a headshot |
| P | Potato | Lowest overall contribution |

</details>

## Changelog

### v2.0.0 — Major update with RT support

- **NEW:** RogueTech (RT) support — sensor-gated weapon names (`UNKNOWN WEAPON` → weapon type → full detail)
- **NEW:** RT approximate salvage (`~N SALVAGEABLE PARTS`) for RT mechs and vehicles
- **NEW:** RT death explosions grouped under a `<unit> EXPLOSION` block after the DESTROYED line, showing each victim's damage/heat; a victim killed by the blast is tagged DESTROYED + salvage inline
- **NEW:** stability tracking — a `+N stability (cur/max)` line per attack, a per-pilot "Stability DMG Dealt" stat, and an "Earthshaker" award (toggle + color)
- **NEW:** friendly pilot callsigns tinted (adjustable color) in the log and initiative
- **NEW:** same-name units are numbered (`#1`, `#2`, …)
- **NEW:** per-pilot "Melee Dealt" stat on the STATS page
- **fix:** a mech cooking off its own ammo from overheating now tags the explosion `(heat)`
- **fix:** camera no longer locks up when hiding the log with the cursor over the window (incl. the settings menu)
- **fix:** a unit's salvage line is no longer dropped when another unit dies at the same moment

Older versions are listed in the full changelog inside [`CombatLog/README.txt`](CombatLog/README.txt).

## Links & contact

- 🌍 **This repo (source & releases):** [github.com/vas7eel/CombatLog](https://github.com/vas7eel/CombatLog)
- 🎮 **Nexus Mods:** [battletech/mods/754](https://www.nexusmods.com/battletech/mods/754)
- 💬 **Discord:** vas7eel
- 🗨️ **Nexus posts** (bug reports & requests): [mods/754?tab=posts](https://www.nexusmods.com/battletech/mods/754?tab=posts)
- 🔴 **Reddit:** [u/vas7eel](https://www.reddit.com/user/vas7eel/)

## License

MIT (see [`CombatLog/LICENSE.txt`](CombatLog/LICENSE.txt)). Free to use and to
include/redistribute in modpacks (RT, BTA, BEX, etc.) — just keep the
copyright/credit notice.

Copyright © 2026 Vas7eel.
