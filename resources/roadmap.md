# Roadmap

This roadmap outlines the development history and planned future features for SwagFishing.

---

## Phase 1-2: Core Systems (Complete)

### Core Fishing
- [x] Custom fishing mechanics replacing vanilla fishing
- [x] 5-tier rarity system (QUARTZ / EMERALD / SAPPHIRE / RUBY / AMETHYST)
- [x] Location-based spawning (biome, time, weather, Y-level, world, region)
- [x] Weighted random selection with rarity multipliers
- [x] Beautiful fish items with colored names and rarity lore

### Data & Persistence
- [x] SQLite database system
- [x] Player profile tracking
- [x] XP and leveling (built-in + FleaJobs integration)
- [x] Essence currency system
- [x] Fish discovery tracking

### UI & Commands
- [x] Fish Codex GUI (Pokédex-style collection viewer)
- [x] `/fish` command structure
- [x] Catch messages with server-wide broadcasts for Ruby/Amethyst

### Admin Tools
- [x] Web-based fish editor
- [x] REST API for fish management
- [x] Password-protected admin panel

### Integrations
- [x] FleaJobs job XP integration
- [x] Vault economy support

---

## Phase 3: Player Storage & Economy (Complete)

### Fish Bag System
- [x] Persistent fish storage GUI (54-slot, paginated)
- [x] Auto-add on catch (configurable)
- [x] Filter by rarity
- [x] Withdraw fish to inventory

### Sell Shop
- [x] GUI for selling fish
- [x] Batch selling (Sell All button)
- [x] Price display per fish
- [x] Vault integration for payments

### Gutting System
- [x] Convert fish to essence via GUI
- [x] Bonus essence vs. selling (configurable multiplier)
- [x] Bulk gutting input slots

### Economy & Progression
- [x] PlaceholderAPI support
- [x] `/fish top` leaderboard
- [x] Tournaments (competitive fishing with leaderboards)
- [x] Deliveries (fishing quests with essence rewards)

### Lore Schemes
- [x] SchemeManager with 5 built-in schemes (one per rarity)
- [x] Custom schemes in custom_schemes.yml
- [x] Auto-applied when fish has empty lore
- [x] Full placeholder set ({displayName}, {rarity}, {xp}, {essence}, etc.)

### Web Editor Enhancements
- [x] Live Minecraft-style tooltip preview (real-time)
- [x] Schemes tab (view, clone, create, apply)
- [x] Clone fish button
- [x] Search and filter bar (by name, rarity, biome)
- [x] Sort controls (by name, rarity, XP, sell price)
- [x] Color picker (inserts &#RRGGBB hex codes at cursor)

---

## Phase 4: Skills, Totems, Bait & Events (Complete)

### Dynamic Events
- [x] EventManager with 3 event types
- [x] FISHING_FRENZY: 2.0× XP + 1.5× essence
- [x] RARE_TIDE: 2.5× weight multiplier for SAPPHIRE+ fish
- [x] ESSENCE_SURGE: 2.0× essence
- [x] Admin commands for start/stop/info
- [x] Server-wide broadcast on event start and end

### Skill Tree
- [x] SkillManager + SkillTreeGUI (54-slot)
- [x] 6 skills implemented (XP Boost, Essence Boost, Rare Finder, Market Expert, Lucky Cast, Delivery Expert)
- [x] Skill point earning system (earned on level-up, with bonus milestones)
- [x] Essence cost per upgrade
- [x] Shift-click refund system (configurable)

### Totem System
- [x] TotemManager + TotemGUI (54-slot)
- [x] 10 totems (basic_luck through ultimate_fisher)
- [x] Level-based unlock progression
- [x] Equip/unequip with configurable max slots
- [x] Admin give command

### Bait System
- [x] BaitManager + BaitGUI (54-slot)
- [x] 15 baits across 4 tiers (Common, Uncommon, Rare, Legendary)
- [x] XP_BOOST, ESSENCE_BOOST, RARE_BOOST, SELL_BOOST effect types
- [x] Limited uses per activation
- [x] Admin give command

### Multiplier Stacking
- [x] Full multiplicative stacking across all systems
- [x] finalXP = base × skillXp × totemXp × eventXp × baitXp
- [x] finalEssence = base × skillEssence × totemEssence × eventEssence × baitEssence

---

## Phase 5: Environmental Systems (Complete)

**Focus:** Make fishing location and conditions matter more

- [x] Weather catch rate bonuses (rain/thunder reduce wait time)
- [x] Depth system (shallow vs. deep fish pools)
- [x] Boat fishing bonus (XP/essence multiplier)
- [x] Visual indicators — actionbar showing active bonuses
- [x] Lunar phases (moon cycle affects rarity weights)
- [x] `/fish weather` — toggle visual rain/storm effects per player

---

## Phase 6: Fish Size, Weight & Records (Planned)

**Focus:** Per-catch variance and competitive records

- [ ] Per-catch randomized size/weight affecting sell price
- [ ] Size integrated into tournament scoring
- [ ] Personal best records per species per player
- [ ] Server-wide all-time catch records leaderboard
- [ ] Cron-scheduled tournaments (specific day/time)

---

## Phase 7: Attunements (Planned)

**Focus:** Craftable rod enhancements

- [ ] Craftable rod enhancements (separate slot system, works alongside ExecutableItems)
- [ ] 10–15 attunement types (Storm Caller, Deep Hook, Lure Master, Essence Draw, etc.)
- [ ] Crafted using essence + fishing materials
- [ ] AttunementGUI + web editor support

---

## Phase 8: Social Features (Planned)

**Focus:** Fishing with friends

- [ ] Fishing Friends system
- [ ] Party fishing (shared XP, proximity bonuses)
- [ ] Party GUI

---

## Phase 9: Nether Fishing (Planned)

**Focus:** Completely new fishing dimension

- [ ] Lava fishing detection
- [ ] Nether-specific fish pool + exclusive rewards

---

## Phase 10: Boss Fish (Planned)

**Focus:** Epic multiplayer encounters

- [ ] Cthulhu boss event
- [ ] Kraken (Ocean boss)
- [ ] Additional boss fish

---

## Phase 11: Polish & Optimization (Planned)

**Focus:** Performance, UX, and quality of life

- [ ] Database optimization + async improvements
- [ ] Achievements system
- [ ] Holographic leaderboards (DecentHolograms/HolographicDisplays)
- [ ] Bait crafting recipes from fishing materials
- [ ] Discord bot integration

---

## Notes

* Phases may be reordered based on community feedback
* Bug fixes and hotfixes released as needed
* Major versions announced in advance

**Want to influence the roadmap?** Submit ideas via GitHub issues!

---

*Last Updated: March 9, 2026*
