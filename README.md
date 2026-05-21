# Cartographer · Wanderer · D2R-Manager

> **A complete tool suite for Diablo 2 Resurrected** — real-time map overlay, autonomous farming automation, and multi-instance launcher, all in one tightly integrated ecosystem.

---

## Design Philosophy

All three tools are built around a core principle: **maximum comfort with minimum configuration.**

Cartographer comes with a sensible configuration that fits all supported classes and builds out of the box. Wanderer auto-detects your character class, learned skills, gear, and breakpoints — there is no profile to write, no script to configure, and no external tool required. Select the areas you want to farm and go.

- **No administrator privileges required**
- **No legacy D2 required**

---

<br/>

# D2R-Manager

## Launcher & Multi-Instance Manager

Launch, manage, and monitor multiple D2R instances side by side — each with its own account, region, and settings. Handles window arrangement, auto-restart on crashes, and provides a live stats dashboard.

### What is D2R-Manager?

D2R-Manager is a desktop application that lets you launch, manage, and monitor multiple D2R instances simultaneously — each with its own Battle.net account, region, and configuration. It works as a launcher, window arranger, and live-stats dashboard in one.

No administrator privileges required. No game files are modified.

### Features at a Glance

#### Account Management

- Store multiple Battle.net accounts (name, email, password)
- Passwords are **encrypted** — tied to your Windows user, never stored in plaintext

#### Profile System

Each account can have multiple profiles defining how D2R is launched

#### Group System (Batch Launch)

Bundle multiple profiles for sequential launch with auto-arrange, monitor targeting, and grid or stacked window layouts. Launch all, launch only missing, or close all with a single click.

#### Quick Launch View

Card-based launcher with real-time search, per-card launch/stop, region cycling, and running status indicators.

#### Wanderer Control Center

Dedicated dashboard showing live stats for all automation instances:

- **Line 1:** Area · Run timer · Games · Games/h · Avg run duration · Deaths · Chickens
- **Line 2:** Magic Find · Max HP · Max Mana · Items stashed · Level + XP% · XP/h

---

<br/>

# Cartographer

## Real-Time Map Overlay

A transparent overlay that renders a live map on top of your game. Features monster radar with immunity colors, map icons, item filter with pickup support, auto-potions, and a full HUD with XP tracker, boss HP, buffs, and drop log.

### What is Cartographer?

Cartographer is a D2R enjoyment enhancer that reveals the map, highlights monsters and loot, and provides a comprehensive HUD — all rendered as a transparent overlay over the game window. It runs silently alongside D2R and is launched automatically by D2R-Manager when you start a game.

### Features

#### Map Overlay

- Real-time transparent overlay with isometric map rendering
- Shows adjacent areas (dungeons, multi-level zones) without switching views
- Automatically reveals unexplored rooms for complete coverage
- **Zoom:** 25–150% (mouse wheel or slider)
- **Opacity:** 10–100%
- **7 visual themes:** Holy Light · Royal Gold · Slate Gray · Ice Blue · Spectral Green · Pink Plasma · Arctic Cyan

#### Monster Radar

Monsters appear as color-coded shapes on the map:

| Shape | Type |
|-------|------|
| Circle | Normal |
| Diamond | Champion |
| Star | Unique |
| Hexagon | Super Unique |

- **Immunity visualization** — shapes split by immunity color (cold, fire, lightning, poison, magic, physical)
- 5 highlight styles: Pulsing Glow · Rotating Symbols · Ground Circle · Double Ring · None
- Separate toggles for normals, bosses/champions, town NPCs, and mercenary

#### Map Icons & Navigation

- Waypoints, exits (with destination names), shrines/wells, chests, portals, quest objects
- Off-screen icons clamp to screen edges
- **Ctrl+Click** any icon to instantly teleport there (requires teleport skill)

#### HUD Elements

| Element | Description |
|---------|-------------|
| Area name & difficulty | Top-right corner |
| Terror Zone indicator | Active TZ in purple |
| XP tracker | XP/h, session gain, time-to-next-level |
| Boss HP bar | Health bar + level, type, auras for Super Uniques & Prime Evils |
| Mercenary HP | Above portrait |
| Session timer | Elapsed playtime |
| Shrine & buff icons | Active shrines, buffs, curses with timers |
| Belt status | 4-column potion grid |
| Drop log | 10 most recent items with rarity colors, 10s fade |
| Party members | Positions on map with area labels |
| Real-time clock | — |

#### Item Filter & Loot

Filters are defined in `itemfilter.yaml`:

- **Global filter** — applies to all characters
- **Per-character filter** — overrides the global filter for that character

**Supported categories:** Runes (by tier), gems (by quality), uniques/sets (by name), rares/magic (with stat thresholds), white/socketed bases (by item code), potions, scrolls, keys, quest items.

**Filter capabilities:** Match by quality, base type, ethereal state, class skills, skill bonuses, and skill procs. Combine conditions with AND/OR logic, require a minimum number of matches, or match combined stat totals. Weighted scoring rules with configurable minimum scores.

**Pickup:** 4 tiles direct range, up to 200 tiles with teleport (Wanderer mode). Capacity checks before pickup. Tome scrolls only when room available.

---

<br/>

# Wanderer

## Autonomous Farming Automation

The full automation system built into Cartographer — exploration, combat, looting, buffing, town management, and game creation — completely unattended. Supports **Sorceress, Paladin, Druid, and Warlock**.

### What is Wanderer?

Wanderer handles the entire farming loop from exploration and combat to looting, buffing, town management, and game creation — completely unattended. Optimized for *Resurrected* and *RotW*. Classic is not supported.

Wanderer is enabled per-profile in D2R-Manager and configured through the Cartographer settings menu (Insert key) or D2R-Manager.

### Design Philosophy

Wanderer prioritizes **ease of use and auto-detection** over configuration complexity.

- Character class and combat mode are detected automatically from your learned skills
- FCR breakpoints, cast timing, and skill levels are resolved in real-time — no manual input needed
- Buffs, auras, and Mercenary state are checked and managed without user intervention
- Area routing, Terror Zone prioritization, and town management are handled autonomously
- Immunity-aware combat rotation adapts to targets automatically

The only thing you need to customize is **which areas to farm** and **what items to pick.**

### Core Systems

| System | Description |
|--------|-------------|
| **Exploration** | Waypoint-driven routing with Terror Zone preference, RunGroup execution |
| **Combat** | Class-specific routines with immunity awareness, FCR-timed casts, safe positioning |
| **Looting** | Reactive item pickup with teleport-to-target and confirmation |
| **Buffs** | CTA buffing, armor, Energy Shield, Thunder Storm, Holy Shield, Druid summons |
| **Town Routine** | 12-step NPC interaction: repair, gamble, stash, potions, merc revive, corpse recovery |
| **Game Management** | Autonomous game creation, exit sequencing, character selection |
| **Chaos Sanctuary** | Seal/Diablo objective handler |
| **Chest Opening** | Reactive chest interaction with teleport |
| **Waypoint Travel** | Multi-act waypoint navigation state machine |
| **Portal Transition** | Quest portal handling |

---

<br/>

## Getting Started

1. **Set up your accounts** in D2R-Manager
2. **Create a profile** with your desired region and settings
3. **Enable Cartographer** for real-time map overlay
4. **Enable Wanderer** for full automation, select your farming areas
5. **Launch** — everything runs automatically

> **Tip:** Start with a single instance and monitor the live stats dashboard. Wanderer's auto-detection handles the rest.
