# 🏰 Claude Life Sim — The Chronicle of Aldwyn

> A medieval village simulation built entirely by AI in a single afternoon.
> Autonomous villagers live, work, talk, fight, marry, and die — and you watch over them as an unseen god.

**▶ Play it live:** [claudelifesim.vercel.app](https://claudelifesim.vercel.app)

**▶ Watch how it was built:** [YouTube — "I Made AI Create a Life Simulator in 4 Hours"](#) *(link coming soon)*

---

## 📜 What is this?

The Chronicle of Aldwyn is a fully autonomous medieval life simulator that runs in your browser. There is no goal, no win condition, no player character. There is only the village.

Villagers wake at dawn, walk to their jobs through the cobbled streets, haggle with merchants, get drunk at the tavern, fall in love beneath the chapel oak, raise children, and eventually die of old age — or fall to bandits, plague, wolves, or the divine wrath of a watching god.

That god is **you**. From the side panel you can summon rain, ignite forests with divine fire, call down plagues, trigger blood moons that empower the bandit raids, or pluck individual villagers off the map and drop them in the river. Every action costs Faith, which regenerates each dawn.

The entire codebase was generated through conversation with Claude (an AI model by Anthropic) over the course of one afternoon — roughly four hours from "I want to build a life sim" to the version you see today.

---

## ✨ Features

### 🧠 Autonomous AI villagers
- **13+ named villagers** at start, each with their own personality, family, job, and home
- **Three social classes** — poor, middle (burghers), wealthy (gentry) — that determine starting gold, housing, voting power, and life trajectory
- **8 jobs** — baker, blacksmith, merchant, farmer, guard, noble, mayor, and child (in school)
- **Needs system** — hunger, energy, social, drunkenness all drift in real time and drive behavior
- **A\* pathfinding** so villagers walk realistic routes around buildings and through gates
- **They go inside buildings** — villagers vanish when they enter a structure, and windows glow at night when occupied

### 💬 Real conversations
- Villagers stop and chat when they meet
- **Floating speech bubbles** pop above their heads with generated lines
- **Click any chatter** to open a transcript panel showing the last 12 lines of their conversation
- Dialogue is **dialect-aware** — Northlanders grunt, Eastreach traders speak formally, Marshford fishers say "Calm seas to ya"
- Lines react to world state — drought, plague, eclipses, and foreigners all trigger contextual dialogue

### ⚔️ Fights & rivalries
- Villagers fight for real reasons: drunken brawls, class envy, low needs, xenophobia, and **persistent grudges** that carry across days
- Combat skill grows from fighting — a farmer who survives enough scrapes can become a Captain of the Guard
- Beaten villagers usually live to remember it, fueling future rivalries

### 👶 Life and death
- **Marriage and reproduction** — adults court, wed, and have children who inherit class from parents
- **Aging** — ~1 year per 8 game days; villagers come of age at 14 (jobs assigned by best skill), can die of old age past 70
- **Permadeath** — villagers killed by hunger, plague, bandits, wolves, or divine wrath are gone forever; the **Chronicle log** preserves their stories

### 🎓 Skill tree
Seven skills — literacy, combat, crafting, farming, charisma, leadership, baking — that grow from doing the relevant activity. At thresholds of 60 and 85, villagers unlock **specializations**:

- *Scholar* → *Sage* (literacy)
- *Veteran* → *Captain of the Guard* (combat)
- *Master Smith* → *Artisan* (crafting)
- *Master Farmer* (farming)
- *Silver-Tongue* → *Charmer* (charisma)
- *Statesman* (leadership)
- *Master Baker* (baking)

### 🌍 Migrants & xenophobia
Travelers arrive at the gates from **five named cultures**, each visually distinct:

- 🌲 **Thornhaven** — hardy forest folk (+farming, +crafting)
- 🐟 **Marshford** — marsh fishers, salty dialect (+farming, +charisma)
- ☀️ **Eastreach** — spice-road merchants with golden turbans (+combat, +leadership)
- 📖 **Greycross** — grey-hooded monks (+literacy, +charisma)
- ⚔️ **the Northlands** — horned warriors (+combat, +crafting)

Foreigners face initial **distrust** from locals — penalty to relationships, exclusion from the mayoralty for years, and risk of drunken xenophobic attacks. Over time, repeated chats build trust and they integrate.

### 🏛️ Politics
- **Mayor elections** every 20 days with **weighted voting** (wealthy 3 votes, middle 2, poor 1 — very medieval)
- The mayor passes laws… well, no, but they collect taxes and gain leadership XP
- When a mayor dies, a snap election is called

### 💰 Economy
- **Treasury** funded by trade taxes and slain bandits
- **Granary** of communal food that feeds the poor in lean times
- **Market** sells bread and ale at prices that fluctuate with supply (and **drought doubles bread prices**)
- **Haggling** — merchants with high charisma get better deals; high-charisma customers haggle them down
- Bakers, farmers, and blacksmiths produce goods proportional to their skill

### ⛈️ Weather
Six weather states, each with mechanical effects:

- ☀️ **Clear** — baseline
- 🌧️ **Rain** — boosts farmer yields
- ❄️ **Snow** — slows movement
- ⛈️ **Storm** — drives everyone indoors, slows movement, lightning flashes
- 🌫️ **Fog** — visual murk
- 🏜️ **Drought** — fields produce less, bread prices spike

### 🌑 Celestial events
- **☾ Blood Moon** — triples bandit raid frequency and gives raiders +HP and damage
- **☉ Eclipse** — darkens the world, villagers panic and lose spirit, dialogue fills with omens

### 🦠 Plague
Sickness spreads villager-to-villager by proximity. Sick villagers move slowly, lose HP, and can die. A cure costs heavy Faith but ends it immediately.

### 🔥 Divine fire
Click any tile to ignite it. Fire **spreads** through forests and fields, burns villagers who step in it, and is genuinely hard to stop without rain or healing.

### 🛡️ Village defenses
- **Palisade walls** ring the village with gates on each cardinal direction
- **Barracks** where guards train
- **Two watchtowers** at opposite corners
- Bandits respect walls and have to slowly path around them, giving guards time to engage
- You can **conscript** any villager into the guard (they get +15 combat XP instantly)

### 🎮 You are God

Every power costs Faith (regenerates +30 per day, starts at 100):

| Category | Power | Cost | Effect |
|---|---|---|---|
| Weather | Clear / Rain / Snow / Storm / Fog / Drought | 5–30 | Change weather instantly |
| Wrath | Divine Fire | 20 | Click a tile to ignite |
| Wrath | Plague | 40 | Sickness spreads through village |
| Wrath | Earthquake | 50 | Damages everyone, sets fires, shakes screen |
| Wrath | Smite | 15 | Click anyone to kill them |
| Celestial | Eclipse | 35 | Darken the world |
| Celestial | Blood Moon | 45 | Empower the bandits |
| Mercy | Bless | 8 | Click a villager — max all stats + skill XP |
| Mercy | Feast | 15 | Fill granary, feed everyone |
| Mercy | Healing | 25 | Restore all HP |
| Mercy | Cure Plague | 50 | End the plague immediately |
| Will | Conscript Guard | 20 | Force a villager into the militia |
| Will | Summon Traveler | 10 | Make a migrant arrive at the gate |

You can also **drag villagers anywhere** with your mouse — drop them in the river to drown them, in the forest where wolves may find them, or on top of an enemy bandit.

---

## 🎬 How it was made

This entire project was built through conversation with **Claude**, an AI model by Anthropic. The process:

1. **Hour 1** — Initial prompt: "build me a medieval life simulator." Got back a working v1 with autonomous AI, day/night, basic economy, mayor elections, and wolf attacks.
2. **Hour 2** — Added drag-to-move, hover tooltips, pathfinding, skill tree with specializations, conversations, persistent rivalries, and haggling merchants.
3. **Hour 3** — Walls and defenses, weather, the full god menu, named migrant cultures, eclipses, blood moons, plague, divine fire, earthquakes, and screen shake.
4. **Hour 4** — Polish, bug fixes, responsive layout, README.

No external dependencies. No libraries. No frameworks. ~3,000 lines of single-file HTML/CSS/JavaScript.

**[Watch the full build on YouTube]** *(coming soon)*

---

## 🛠️ Running locally

No build step. No `npm install`. Just:

```bash
git clone https://github.com/CryptoGatsu/claudelifesim.git
cd claudelifesim
# open index.html in any browser
```

Or with VS Code's Live Server extension, right-click `index.html` → "Open with Live Server."

---

## 🗺️ Code structure

Everything lives in `index.html` for now (yes, all of it). Inside the `<script>` tag, the code is broken into **28 numbered sections** for easy navigation:

```
SECTION 1.  CONSTANTS & CANVAS
SECTION 2.  TIME (day/night cycle)
SECTION 3.  MAP, TILES, BUILDINGS, WALLS
SECTION 4.  ECONOMY
SECTION 5.  SKILLS
SECTION 6.  VILLAGER MODEL
SECTION 7.  ORIGINS / CULTURES
SECTION 8.  DIALOGUE GENERATION
SECTION 9.  WORLD INIT
SECTION 10. PATHFINDING (A*)
SECTION 11. AI DECISIONS
SECTION 12. UPDATE LOOP
SECTION 13. JOBS & SKILL XP
SECTION 14. CONVERSATIONS
SECTION 15. FIGHTS & RIVALRIES
SECTION 16. COURTSHIP & REPRODUCTION
SECTION 17. DEATH
SECTION 18. ELECTIONS
SECTION 19. THREATS (wolves, bandits)
SECTION 20. MIGRATION
SECTION 21. WEATHER & PLAGUE
SECTION 22. GOD POWERS
SECTION 23. RENDERING
SECTION 24. HUD / TOOLTIP / TRANSCRIPT
SECTION 25. LOG
SECTION 26. INPUT
SECTION 27. MAIN LOOP
SECTION 28. BOOT
```

To find any system, search for `SECTION N:` in your editor.

---

## 🧪 Extending it

The code is designed to be hackable. Some easy first additions:

**Add a new culture** — edit `SECTION 7: ORIGINS`:
```javascript
deepwood: {
  id: 'deepwood', name: 'Deepwood',
  color: '#2a3a2a', accent: '#a0c0a0',
  bonuses: { combat: 10, literacy: 8 },
  dialect: 'gruff',
  firstNames: ['Treebeard','Mossfoot','Acorn'],
  lastNames: ['of the Old Forest', 'Greenleaf'],
  desc: 'silent forest folk',
}
```

**Add a new god power** — edit `SECTION 22: GOD POWERS`:
```javascript
locust: {
  cost: 35, instant: true, fn: () => {
    ECON.granaryFood = Math.floor(ECON.granaryFood * 0.3);
    log('A plague of locusts strips the fields bare.', 'god');
  }
}
```

Then add a button in the HTML with `data-power="locust"`.

**Add a new tile type** — edit the tile-generation loop in `SECTION 3`, then add a case to `drawTile()` in `SECTION 23`.

---

## 🐛 Known limits

This is a 4-hour AI build, not a production game. Some honest caveats:

- **No save state.** Refresh = new village. (Coming soon.)
- **Performance degrades past ~50 villagers** because AI loops are O(n²). Needs a spatial grid.
- **Buildings can't be built or destroyed.** The map is fixed.
- **Lifespan is fast** — ~80 minutes per villager at 1× speed. Tune the day length in `SECTION 2` if you want slower generations.
- **The economy doesn't have inflation or scarcity death-spirals.** Treasury just grows.
- **AI is reactive, not goal-oriented.** No long-term plans or memory beyond relationship scores.

The plan is to fix all of this. Roadmap below.

---

## 🗺️ Roadmap

- [ ] **Save/load** via localStorage so refreshing doesn't kill Aldwyn
- [ ] **Spatial grid** so the village can grow to 200+ villagers without lag
- [ ] **Personality traits** (greedy/generous, brave/cowardly, devout/skeptical) that bias decisions
- [ ] **Year cycle with seasons** — harsh winters that strain food, spring planting, autumn harvest festivals
- [ ] **Family trees** with generational history
- [ ] **A persistent graveyard** you can visit
- [ ] **Building construction** — village grows when population pressures housing
- [ ] **Code refactor** into separate modules (`simulation.js`, `renderer.js`, etc.)
- [ ] **Server-side simulation** running 24/7 with WebSocket clients — anyone can drop in and watch the village
- [ ] **Database persistence** so the village outlives any one server

---

## 🤖 About the AI build process

This project is an experiment in **conversational software development** — I describe what I want, the AI writes the code, I run it, I describe what's wrong or what should be added, and we iterate.

The full conversation history is essentially the design doc. There were no specs, no diagrams, no architecture sketches. Just back-and-forth.

What surprised me most:

- **It nailed aesthetics** without me asking. The illuminated-manuscript styling, the blackletter title, the parchment textures — all unprompted.
- **It pushed back on scope** at the start, warning that "Dwarf Fortress in one afternoon" isn't realistic, then proposed a smaller v1 that was still ambitious.
- **It asked good clarifying questions** before big features — "Should fights persist as rivalries? Should foreigners be visually distinct?" — rather than guessing.
- **Sectioning the code** for VS Code navigation was its own idea, knowing I'd want to extend it later.

The hard parts AI struggled with: subtle CSS layout bugs (the responsive breakpoint issue that crushed the map), and balancing simulation values (fertility vs mortality, faith regen vs power costs) which really need playtesting.

---

## 📺 The YouTube video

If you're here from the video, welcome. Drop a star ⭐ if you'd watch a follow-up where I push this to 24/7 server-hosted and let it run for a month.

---

## 📄 License

MIT. Fork it, mod it, remix it. If you build something cool from this, I'd love to see it — tag me on whatever platform.

---

*Built with Claude · Hosted on Vercel · Made in one night*
