═══════════════════════════════════════════════════════════
  COMBATLOG MOD v2.1.1 - README
  A BattleTech mod by Vas7eel
═══════════════════════════════════════════════════════════

OVERVIEW
--------
CombatLog displays a real-time combat log with stats during battles,
showing all damage dealt with to-hit %, weapons fired, 
locations destroyed, pilot injuries and ejections, and mech 
deaths as they happen. It respects fog of war, meaning 
sources of damage that you haven't spotted are shown as 
UNKNOWN. It shows combat initiative order at the start of 
each round, this also respects Fog of War. This mod also
tracks stats of each pilot as well as overall lance performance
for each mission. This mod works with Vanilla, BTAU, BEXT,
and RT.


LICENSE
-------
MIT License (see LICENSE.txt). Free to use and to include/redistribute in
modpacks (RT, BTA, BEX, etc.) — just keep the copyright/credit notice.
Copyright (c) 2026 Vas7eel.


CONTROLS
--------
  L             - Toggle log visibility on/off
  K             - Toggle between log and stats view
  Drag title    - Move the window
  ◢ grip        - Resize the window from bottom-right corner
  - / +         - Decrease / increase font size
  40%           - Cycle background opacity
                  (0%, 20%, 40%, 60%, 80%, 100%)
  ✕             - Clear the combat log
  LOCK          - Lock/unlock auto-scroll to the newest entry
  LOG           - Combat Log main panel
  STATS         - Mission and pilot stats (LIVE)
  PREFS         - Customize CombatLog, changes are saved (LIVE)


STATS VIEW
----------
  Press K to toggle the log/stats panels. Tabs across the top
  switch between pilots and the mission overview.

  MISSION tab
    - Live mission totals (shots, hits, damage, kills)
    - Pilot rankings sorted by damage dealt
    - Awards tracking with thresholds — shows current
      leader during combat and winner at mission end

  Awards
    ★ Top Gun            Most damage dealt
    ⛊ Iron Wall          Most damage taken
    ☠ Destroyer          Most kills
    ◎ Deadeye             Highest hit percentage
    ♛ Exhibitionist      Most attacks received
    ☘ Can't Touch This  Most potential damage evaded
    ✚ It's Just a Flesh  Wound  Most injuries suffered
    ⚔ Sadist             Most injuries caused
    ✊ Rock'em Sock'em    Most melee damage dealt
    ♨ Flamin' Hot         Highest peak heat reached
    ⚠ This is Fine       Most turns spent overheated
    ✷ Purify by Fire     Most heat damage dealt to enemies
    ☄ Earthshaker        Most stability damage dealt
    ⊙ Headhunter          Killed a mech with a headshot
    P Potato              Lowest overall contribution


  Pilot tabs
    Per-pilot breakdown including offense, defense,
    weapon stats, attacker breakdown, and nemesis.
    Hover over any column header for a description.

  PREFS tab
    In-game toggles and color configuration. Changes
    are saved automatically to CombatLog_prefs.json.


CHANGELOG
---------
 v2.1.1
    - fix: scrolling up with the mouse wheel after unlocking the log no
      longer instantly re-locks and snaps back to the bottom
 v2.1.0
    - NEW: Improved performance — log caching only rebuilds log lines 
      when content changes, greatly improving performance andcutting down 
      frame hiccups in heavy fights
    - NEW: "Show Enemy Initiative" toggle (under Show Initiative) to
      include or hide enemy units in the round initiative list
    - NEW: "Remember Sensor Info" toggle (RT, off by default) — the log
      keeps the best sensor read seen for each unit this mission
    - improved: only weapon-delivered heat (flamers etc) now counts
      toward "Heat Damage Dealt" and the Purify by Fire award; ammo-
      explosion and terrain heat are still shown but no longer inflate
      heat stats
    - fix: the resize grip is no longer hidden behind the buttons when
      the window is shrunk very small
    - fix: RogueTech sensor-gated UNIT NAMES — an enemy's name is now
      revealed with your sensor lock, matching the target panel:
      UNKNOWN MECH -> chassis ("UrbanMech") -> full variant ("UM-R60"),
      in both the log and initiative (2.0.0 gated weapon names and units 
      were not fully correct)
 v2.0.0 - Major update with RT support, new features and improvements:
    - NEW: RogueTech (RT) support — adds RT sensor-gated weapon names
      (UNKNOWN WEAPON -> WEAPON TYPE -> WEAPON DETAIL)
    - NEW: RT approximate salvage ("~N SALVAGEABLE PARTS") for RT mechs and vehicles
    - NEW: RT death explosions are grouped under a "<unit> EXPLOSION" block after the
      DESTROYED line, showing each victim's damage/heat; a victim killed by the
      blast is tagged DESTROYED + salvage inline
    - NEW: stability tracking — a "+N stability (cur/max)" line per attack, a
      per-pilot "Stability DMG Dealt" stat, and an "Earthshaker" award (toggle + color)
    - NEW: friendly pilot callsigns are now tinted (adjustable color) in the log and
      initiative, to help tell them apart from enemies at a glance
    - NEW: same-name units are now numbered (#1, #2, ...) 
    - NEW: per-pilot "Melee Dealt" stat on the STATS page
    - fix: a mech that cooks off its own ammo from overheating now tags the
      explosion "(heat)"
    - fix: camera no longer locks up when hiding the log with the cursor over the
      window (including from the settings menu)
    - fix: a unit's salvage line is no longer dropped when another unit dies at the
      same moment
 v1.9.9
    - NEW: "Attack Damage Total" line — adds an italic "Total: N hits = X dmg"
      summary under each multi-weapon attack (on by default; toggle + color in
      PREFS). It includes secondary ammo/component-explosion damage, so it
      reflects the full damage the target took that attack
    - NEW: the log now auto-hides during dialog/conversation screens (priority-
      mission briefings, crew conversations) so it no longer sits over the dialog
      — respects the "Auto-hide ArgoLog" pref; press L to show it anytime
    - fix: ammo/component explosions whose name didn't resolve no longer show
      "{0} EXPLOSION" — they now fall back to a readable component name
 v1.9.8
    - NEW: Heat & overheat logging — logs when a mech goes over its heat redline
      (shown as % of redline, e.g. 133%), heat structure damage, and shutdowns
      including override pass/fail. Configurable in the new PREFS "HEAT" section
      (toggle + log threshold)
    - NEW: flamer/inferno heat dealt to a target now shows as "+N heat", and ammo
      explosions caused by heat are tagged "(heat)"
    - NEW: AMS interceptions are logged ("AMS: x/y intercepted")
    - NEW: LOCK button (left of the LOG tab) to lock/unlock auto-scroll-to-bottom
    - NEW: three heat awards — Flamin' Hot (highest peak heat), This is Fine (most
      turns overheated), Purify by Fire (most heat dealt) — plus per-pilot heat
      stats (peak heat, turns overheated, heat dealt)
    - fix: late crit / injury / health / AMS / knockdown / panic floaties now
      attach to the attack that caused them instead of the next one
    - fix: the overheat line now prints after the attack that caused the heat
 v1.9.7
    - Argo and in-mission now keep SEPARATE window layouts (position, size, font,
      opacity) so switching context no longer carries over the other layout
      (new toggle "Separate Argo/Combat layouts", default ON)
    - new toggle "Auto-hide ArgoLog off main screen" (default ON): on the Argo the
      log shows only on the main ship screen and hides in sub-menus (mechbay,
      barracks, etc.) — press L to bring it up anywhere
    - the log now opens to LOG when a mission starts, and back to ARGO when you
      return to the Argo
    - K is context-aware: on the Argo it cycles LOG -> STATS -> ARGO; in a mission
      it toggles LOG <-> STATS
    - L now opens the log at any time (it no longer auto-shows on the main menu)
    - renamed the ARGO tab (was clipping) and removed the now-redundant
      "Show ArgoLog on Argo" toggle
    - fixed auto-scroll freezing partway during busy rounds (LOG and ARGO panes)
    - "DEPLOY" no longer appears in the round initiative list
    - weapon "Best vs <target>" now shows the target a weapon actually hit in
      multi-target attacks, not always the primary target
    - Potato award re-weighted (damage counts for more; "times shot at" counts for
      less) and its tooltip now explains the scoring formula
    - every PREFS toggle now has a hover tooltip explaining what it does
 v1.9.6
    - NEW: ArgoLog — an out-of-combat log pane (click the ARGO tab) that records
      what happens on the Argo, grouped under the in-game date
        - pilots returning to duty, repairs/refits, flashpoints added/removed
        - random events: logs the event, the choice you made, and the outcome
          (morale, reputation, C-bills, tags) — ComStar broadcasts included
        - monthly financial report (operating expenses and remaining funds)
        - budget morale change when you set the monthly expense level
    - ArgoLog persists for the play session and clears when you load a game
    - new toggle "Show ArgoLog on Argo": on = the log opens automatically on the
      Argo (ARGO pane); off = press L to open it
    - clear (✕) is context-aware: clears the ArgoLog while on the ARGO tab,
      otherwise clears the combat log
 v1.9.5
    - extraction fix — units that successfully extract/escape are no longer
      logged as DESTROYED or counted as kills
    - critical hits and component-destroyed messages now log under the correct
      attack instead of sometimes jumping to the next attacker
    - "all shots missed" and other attack lines now stay in their own round
      instead of occasionally appearing at the top of the next round
    - PREFS toggle labels are now aligned a little better next to their ON/OFF button
    - "Reset to Defaults" button no longer clips its text at larger font sizes
 v1.9.4
    - added logging for heat damage 
    - added called shots with location logging
    - added missed all shots line for attacks that miss with all weapons
    - salvage line now consistently appears after MECH DESTROYED, across all mods
    - Battle Armor is logged properly with BTAU (and might work with RT)
    - Total enemy kills now include unattributed deaths (heat/ammo/indirect)
    - Rock'em Sock'em award for most melee damage
    - Award tooltips show full pilot ranking — winner, runner up, participants
    - fixed DEPLOY pilot placeholder in log and stats
    - Auto-Clear on Mission Start toggle, saved in prefs
    - Pref menu cleanup, added section headers and tooltips
    - Various bug fixes
 v1.9.3
    - lots of bug fixes
    - legibility changes, switched log to monospace font, same as stats now
    - switched from 5x6=30dmg hit/dmg format to 5 hits = 30dmg
    - made changes to stats page, better use of column width 
    - Ejections now report salvage properly
    - Deaths in non player turns caused by heat/explosions also now show salvage

  v1.9.2
    - Major update with LOG, STATS, PREFS panels
    - PREFS panel to adjust CombatLog options, prefs are saved
    - Allows custom color picker for LOG events
    - STATS panel w/Mission tab with live combat tracking across all pilots
    - PilotName tabs with live combat tracking for each pilot
    - Awards system show current leader during combat, winner after
    - Tooltips on all stats column headers
    - Tooltips on award names showing their criteria
    - End Visible toggle — keep log open after mission ends
    - Added K and L hotkeys, K toggles between LOGS and Stats, L show/hide window
    - Added version in titlebar
    - Various bug fixes that were reported by multiple users, thank you for the feedback
  v1.8
    - Pilot ejections now logged
    - Initiative orders printed at the start of each round
  v1.7
    - Better BTA specific logging
    - Panic states (Unsettled, Stressed, Panicked) shown in yellow
    - BTA specific pilot injuries with severity shown in pink
    - Bleeding out warnings shown in red
    - Consciousness threshold tracking shown in pink
    - Pilot incapacitated shown in red
    - Pilot health status shown in white (works for Vanilla too)
    - Salvageable parts shown in green
    - Each floatie type has its own configurable color in mod.json
  v1.6
    - Added Fog of War option in mod.json, so any damage coming from sources that 
      are not fully visible, show up as UNKNOWN rather than the Mech Name
    - Fixed Vehicle dmg locations in BTA, so they dont show LeftArm, LeftLeg etc.
    - Added option in mod.json to start CombatLog visible in battle or not
  v1.5
    - To-hit percentage tracking per weapon line, with mod.json option to disable
    - Melee color changed to cyan for better readability
  v1.4
    - Vehicle/turret tracking fixes
    - Ammo explosions working
  v1.3
    - Accurate weapon attribution via TakeWeaponDamage patch
    - Armor vs structure damage coloring
    - Pilot injury tracking with reason  


INSTALLATION
------------
  1. Ensure ModTek is installed
  2. Copy the CombatLog folder to:
     BATTLETECH/Mods/CombatLog/
  3. Launch the game


COMPATIBILITY
-------------
  BattleTech version: 1.9.1
  ModTek version:     4.2.0+, 4.4.1+, 4.5.0+
  HarmonyX version:   2.15.0+
  BTAU:               Latest
  BEXT:               Latest
  RT:                 Latest


LINKS & CONTACT
---------------
GitHub:                     https://github.com/vas7eel/CombatLog
Nexus Mods:                 https://www.nexusmods.com/battletech/mods/754
Discord:                    vas7eel
Bug reports / requests:     https://www.nexusmods.com/battletech/mods/754?tab=posts
Reddit:                     https://www.reddit.com/user/vas7eel/
    

SETTINGS (mod.json)
-------------------

  DebugLog
    true/false - enables debug logging to output_log.txt
    Default: false

  StartVisible
    true/false - show log automatically when combat starts
    Default: true

  EndVisible
    true/false - keep log visible after mission ends
    Default: false

  FogOfWarNames
    true/false - show UNKNOWN for unspotted attackers
    Default: true

  ShowToHitChance
    true/false - show to-hit % per weapon line in the log
    Default: true

  ShowInitiative
    true/false - show initiative order at round start
    Default: true

  COLOR SETTINGS
  --------------
  All colors support three formats:

  1. Named colors:
     WHITE, RED, GREEN, BLUE, YELLOW, ORANGE, PINK,
     GREY, GRAY, CYAN, MAGENTA, BLACK, PURPLE, GOLD

  2. Hex format:
     "#FF8C00"

  3. RGB format (0-255 or 0.0-1.0):
     "rgb(255,140,0)"
     "rgb(1.0,0.55,0.0)"

  Colors can also be changed in-game via the PREFS tab.
  In-game changes are saved to CombatLog_prefs.json and
  take priority over mod.json on subsequent launches.

  ArmorDamageColor
    Color for normal armor hits.
    Default: "WHITE"

  StructureDamageColor
    Color for hits that reach the structure.
    Default: "#FF8C00"

  MeleeDamageColor
    Color for melee attacks.
    Default: "CYAN"

  SecondaryDamageColor
    Color for secondary/spillover damage.
    Default: "ORANGE"

  MechDestroyedColor
    Color for mech destroyed entries.
    Default: "#FF2222"

  DestroyedLocationColor
    Color for location destroyed entries.
    Default: "#FF4444"

  PilotInjuryColor
    Color for pilot injury entries.
    Default: "PINK"

  RoundBreakColor
    Color for round break separators.
    Default: "#888888"

  PanicColor
    Color for panic state entries.
    Default: "YELLOW"

  ThresholdColor
    Color for consciousness threshold entries.
    Default: "ORANGE"

  BleedColor
    Color for bleeding out warnings.
    Default: "RED"

  IncapColor
    Color for pilot incapacitated entries.
    Default: "RED"

  HealthColor
    Color for pilot health status entries.
    Default: "WHITE"

  SalvageColor
    Color for salvageable parts entries.
    Default: "GREEN"

 
LAYOUT FILE
-----------
CombatLog_layout.json is auto-generated and stores:
  - Window position (X, Y)
  - Window size (Width, Height)
  - Font size
  - Background opacity

Delete this file to reset the window to default position
and size.

PREFS FILE
----------
CombatLog_prefs.json is auto-generated when settings are
changed in-game via the PREFS tab. It stores toggles and
color overrides. Delete this file to revert to mod.json
defaults, or use the Reset to Defaults button in the
PREFS tab.

NOTE: Window position, size, font size, and opacity are
saved automatically to CombatLog_layout.json and will
persist between sessions. You do not need to edit these
in mod.json after the first launch.