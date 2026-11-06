# WEXUR — Wave EXpansion URge

**A strategic merge tower-defense game built as a single-file HTML5 application.**

![WEXUR](https://img.shields.io/badge/version-1.1-blue) ![License](https://img.shields.io/badge/license-Proprietary-red) ![Languages](https://img.shields.io/badge/languages-RU%20%7C%20EN%20%7C%20ES%20%7C%20FR%20%7C%20ZH-green)

---

## 🎮 About the Game

**WEXUR** (Wave EXpansion URge) is an original merge-based tower defense where you command a team of 5 unique units against endless waves of monsters. Unlike typical TD games, victory depends on **deep synergy systems**, **procedural merges**, and **strategic sacrifices**.

### ✨ Key Features

- **60+ Unique Units** across 4 classes:
  - 🟠 **Attack** — direct damage dealers (Sunflower, Donut, Aster, Cherry, Grape, Planet, Diamond, Disc, Maple, Juice, Teddy, Sakura, Lion, Algae, Pumpkin, Tangerine, Ball, Teapot, Radar, Fuel, Airport, Sleepy, Candy, Urn, Bubble Tea, Worm, Star, Capricorn, Lilac, Billiard, Eagle…)
  - 🟡 **Semi-Support** — hybrid fighters (Can, Hourglass, Lava, Eclipse, Kiwi, Barrel, Solar, Dog, Yarn, Cloud, Balloon, Triangle, Melon, Extinguisher, Fern, Heart, Amur, Lady, Station, Magnet)
  - 🟢 **Support** — utility & control (Hook, Rose, Snow, Coconut, Disco Ball, Clover, Graph, Battery, Portal, Olive, Salt, Vase, Anchor, Gift)
  - ⚫ **Risk** — high-reward / high-cost (Translator, Uranium, Plug, Gem, Key, Snake, Camera)
- **Procedural Merge System** — same-rank merging with per-unit "stay probability" (e.g., Sunflower keeps its identity 75% of the time, while Star only does so 5%). Special pairs like 🍊+🫖 or 🎈+🟢 have custom outcomes.
- **Deep Synergy Engine** — adjacency bonuses between specific units (e.g., 🏵️+♑ grant both +20% damage; 🌸 boosts 🍒 by +2%; 📐 and 💠 boost each other by +13%).
- **12 Monster Types** including bosses (🐲), fast flyers (🚁), tanks (🐷, 🦖 Dino), armor-breakers (🎠 Carousel), and special threats (⛄ Frost, 👻 Ghost).
- **Local Duel Mode** — two players pick teams independently and battle side-by-side on one device.
- **Records System** — three leaderboards (Normal / Challenge / Duels) saved locally via `localStorage`.
- **5-Language Localization** — Russian, English, Spanish, French, Chinese (switchable in-game).
- **Fully Offline** — no server, no accounts, no tracking. Just open the `.html` file.

---

## 🚀 How to Run

No build tools required. Simply download `WEXUR.html` and open it in any modern browser (Chrome, Firefox, Edge, Safari, Brave…). Works on desktop and mobile.

```bash
# Option 1: just double-click the file
open WEXUR.html

# Option 2: serve locally for best experience
python3 -m http.server 8000
# then visit http://localhost:8000/WEXUR.html
```

---

## 🧠 Core Mechanics

### Merging Rules
- Drag unit A onto unit B of the **same rank** to merge.
- Resulting unit gains **+1 level**; tier (★) is preserved separately.
- Each unit has a **stay probability**: chance it remains itself after merge. Otherwise it transforms into another deck unit randomly.
- Special cases:
  - 🍊 + 🫖 → always becomes one of them (+1 lvl)
  - 🎈 + anything → mostly absorbs the other's identity
  - 💿 + 💿 → roulette outcome (may even destroy both!)
  - 📈 + 📈 → marks a target unit for +1 rank upgrade
  - 🔁 Translator duplicates partner or dies trying
  - 🎥 Camera either upgrades to Lvl 10 or resets everyone

### Sacrifices
- Drag a Level 1 movable unit onto ⚱️ **Urn** → 35% chance Urn gains +1 rank.
- Drag 🚉 **Station** onto ⚱️ → guaranteed +35 ✨ sparkles.

### Adjacency Bonuses (examples)
| Pair | Effect |
|------|--------|
| 🏵️ ↔ ♑ | Both get +20% damage |
| 🌸 → 🍒 | +2% damage per Sakura neighbor |
| 📐 ↔  | +13% damage each way |
|  → 🍁 | +40% damage once |
| 🎃 → 🧋 | +20% damage once |
| ⚱️/🛢️/🔌 → 🧋 | +22% rate once |
| 📈 → ♑ | ×3 damage per Graph neighbor |
| 🦮 cluster | +15% rate per Dog neighbor |
| 🌹 → 🦮 | +12% damage |
| 🪐 → ☀️ | +9% damage |
| 📡 → 💠 | +5% portal chance |

### Immovable Units
Some units cannot move from their cell: 🪩 disco ball, ☢️ uranium, 🎥 camera,  dog, 🪴 fern, 🫀 heart, 💟 amur, 🧸 teddy, 📈 graph, 🌑 eclipse, 🐍 snake, 🚉 station, ⏳ hourglass, ♑ capricorn.

### Hidden Units
- 🍅 Tomato — spawned by 🪱 Worm, attacks only 🐲 Boss.
- 🪵 Buratino — appears when you collect 7 🗝️ Keys; self-grows every 15s until stopping.

---

## 🌐 Modes

| Mode | Description |
|------|-------------|
| ▶️ Play | Classic mode — pick your 5 starting units freely |
| 🎲 Challenge | Random 5-unit deck assigned at start |
| 👥 Duel | Two-player hotseat match on split screen |
| 📖 Guide | Browse all units, stats, abilities, and simulate ranks/stars |
| ⚠️ Synergy | Full rulebook of every interaction |
| 🏆 Records | Local leaderboard with starring feature |
| ⚖️ Rights | Authorship notice and license text |

---

## 🛠 Tech Stack

- **Pure Vanilla JavaScript** (no frameworks, no dependencies except optional PeerJS CDN which has been removed in v1.1)
- **Single HTML file** (~200 KB minified) containing CSS + JS + assets-as-emoji
- **Canvas API** for path rendering and projectiles
- **DOM overlay** for grid cells and floating numbers
- **localStorage** for saves, records, language preference
- **SHA-256 fingerprint** computed at runtime for integrity verification

---

## 📜 License

See [LICENSE.txt](./LICENSE.txt). In short:

> © 2026 Daniil Vasilievich Myagkov. All rights reserved.  
> You may host and share this file unchanged, with authorship intact.  
> Commercial use, paid redistribution, and closed-source derivatives require written permission.

---

## 👤 Author

**Daniil Vasilievich Myagkov** (Мягков Даниил Васильевич)  
Also creator of [QFTM-1024](https://github.com/yourusername/qftm-1024) — a scientific personality typing system based on Big Five.

---

## 🙏 Acknowledgements

- Emoji set: Unicode Consortium standard emoji glyphs rendered by OS fonts.
- Inspiration: classic merge games (2048, Merge Dragons!), tower defense staples (Bloons TD, Kingdom Rush), and roguelite deck-builders (Slay the Spire).
- Testing feedback: friends and family who endured dozens of balance iterations.

---

## 📬 Contact

For commercial licensing inquiries, derivative permissions, or bug reports, please open an issue on GitHub or contact the author directly.

---

*Built with ❤️ and far too many hours of playtesting.*
