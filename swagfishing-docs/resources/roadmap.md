# 🗺️ Roadmap

This roadmap outlines planned features for SwagFishing, organized by development phases.

## ✅ Completed (Phase 1-2)

### Core Systems
- [x] Custom fishing mechanics
- [x] 5-tier rarity system
- [x] 14 base fish collection
- [x] Location-based spawning (biome, time, weather, Y-level)
- [x] Weighted random selection
- [x] Beautiful fish items with auto-generated lore

### Data & Persistence
- [x] SQLite database system
- [x] Player profile tracking
- [x] XP and leveling (built-in + FleaJobs integration)
- [x] Essence currency system
- [x] Fish discovery tracking

### UI & Commands
- [x] Fish Codex GUI (Pokédex-style collection viewer)
- [x] Admin menu GUI
- [x] Custom fish manager GUI
- [x] `/swagfish` command structure
- [x] Beautiful catch messages

### Admin Tools
- [x] Web-based fish editor
- [x] REST API for fish management
- [x] Password-protected admin panel
- [x] Live fish creation/editing/deletion

### Integration
- [x] FleaJobs job XP integration
- [x] Vault economy support
- [x] Fallback systems for optional dependencies

---

## 🚧 Phase 3: Player Storage & Economy (Current)

**Focus:** Give players ways to manage and profit from their catches

### Fish Bag System
- [ ] Inventory-style storage GUI
- [ ] Store caught fish
- [ ] Browse collection
- [ ] Withdraw fish to inventory
- [ ] Sort by rarity, type, date caught

### Sell Shop
- [ ] GUI for selling fish
- [ ] Batch selling
- [ ] Price display
- [ ] Confirmation system
- [ ] Vault integration for payments

### Gutting System
- [ ] Convert fish → essence
- [ ] Bonus essence from gutting
- [ ] GUI for gutting process
- [ ] Bulk gutting option

**Estimated Completion:** 1-2 weeks

---

## 📊 Phase 4: Environmental Systems

**Focus:** Make fishing location and conditions matter

### Weather Bonuses
- [ ] Rain: +10% rare fish chance
- [ ] Thunder: +20% rare fish + 15% XP boost
- [ ] Clear weather requirements for specific fish
- [ ] Visual indicators when bonuses active

### Depth System
- [ ] Calculate water depth below fishing hook
- [ ] Shallow (< 3 blocks): Common fish only
- [ ] Medium (3-10 blocks): Common + Uncommon
- [ ] Deep (10+ blocks): All rarities
- [ ] New fish property: `min-depth`

### Boat Fishing Bonus
- [ ] Detect when fishing from boat
- [ ] +10% catch rate boost (secret bonus)
- [ ] Special message on first discovery

### Standing in Water
- [ ] Detect player standing in water
- [ ] +5% catch rate boost
- [ ] Stackable with other bonuses

**Estimated Completion:** 1 week

---

## 👥 Phase 5: Social Features

**Focus:** Fishing with friends

### Fishing Friends System
- [ ] Add/remove friends list
- [ ] `/swagfish friends` commands
- [ ] Friends list GUI
- [ ] Online status indicators

### Party Fishing
- [ ] Create/join fishing parties
- [ ] `/swagfish party` commands
- [ ] Proximity-based (must be within 50 blocks)
- [ ] Shared XP pool (split evenly)
- [ ] Party bonus: +5% XP per member
- [ ] Friend bonus: Additional +5% if fishing with friends

### Party GUI
- [ ] View party members
- [ ] Invite players
- [ ] Kick members
- [ ] Leave party
- [ ] See combined stats

**Estimated Completion:** 2 weeks

---

## 🎉 Phase 6: Events & Tournaments

**Focus:** Competitive and cooperative content

### Random Server Events
- [ ] Fishing Frenzy (2x catch rate, 30 min)
- [ ] Lucky Hour (better rarity drops, 1 hour)
- [ ] Essence Surge (2x essence, 45 min)
- [ ] Server-wide announcements
- [ ] Countdown timers
- [ ] Random scheduling (every 4-8 hours)
- [ ] Config-based event customization

### Tournament Expansion
- [ ] Automated tournament scheduling
- [ ] Multiple tournament types:
  - Most fish caught
  - Biggest fish
  - Rarest fish
  - Total value
- [ ] Leaderboard GUI
- [ ] Reward distribution
- [ ] Tournament history

### Delivery System Expansion
- [ ] Daily fishing quests
- [ ] "Bring me X fish" missions
- [ ] Randomized deliveries
- [ ] Scaling rewards
- [ ] Streak bonuses

**Estimated Completion:** 2-3 weeks

---

## 🌳 Phase 7: Skill Tree Implementation

**Focus:** Long-term progression and customization

### Skill System
- [ ] Skill tree GUI (4 tiers)
- [ ] Skill point earning system
- [ ] Skill unlock requirements
- [ ] Skill descriptions & previews

### Tier 1 Skills (Entry-level)
- [ ] Lucky Line (+2% rare fish/level, max +10%)
- [ ] Quick Hook (-5% wait time/level, max -25%)
- [ ] Treasure Hunter (+5% essence/level, max +25%)
- [ ] Haggler (+3% sell price/level, max +15%)

### Tier 2 Skills (Mid-tier)
- [ ] Storm Fisher (2x weather bonuses)
- [ ] Deep Diver (catch rare fish in shallow water)
- [ ] Night Owl (+20% XP at night)
- [ ] Party Leader (+10% party bonus)

### Tier 3 Skills (Advanced)
- [ ] Master Angler (+5% double fish chance)
- [ ] Essence Surge (10% double essence chance)
- [ ] Nether Adaptation (unlock nether fishing)
- [ ] Fortune's Favor (catch fish 1 tier higher)

### Tier 4 Skills (Master)
- [ ] Legendary Hunter (Mythical spawn +50%)
- [ ] Cthulhu's Challenger (+25% boss damage)
- [ ] Master Gutter (2x gutting essence)
- [ ] Ocean's Blessing (all buffs stack)

**Estimated Completion:** 2 weeks

---

## 🗿 Phase 8: Totems & Buffs

**Focus:** Temporary power-ups

### Totem System
- [ ] Totem crafting (essence + materials)
- [ ] Totem inventory GUI
- [ ] Equip/unequip totems
- [ ] Multiple totem slots (unlock with skills)
- [ ] Totem durability

### Totem Types
- [ ] Speed Totem (faster bites)
- [ ] Luck Totem (better rarities)
- [ ] Wealth Totem (more money)
- [ ] Essence Totem (more essence)
- [ ] Experience Totem (more XP)
- [ ] Combo totems (multiple effects)

**Estimated Completion:** 1-2 weeks

---

## 🔥 Phase 9: Nether Fishing

**Focus:** Completely new fishing dimension

### Nether Mechanics
- [ ] Fishing in lava detection
- [ ] Nether-specific fish pool (15-20 fish)
- [ ] Fireproof fishing rod requirement or skill
- [ ] Unique lava fishing particles
- [ ] Nether ambient sounds

### Nether Fish
- [ ] Design nether fish (Magma Bass, Lava Eel, etc.)
- [ ] Hellfire Tuna (legendary)
- [ ] Obsidian Pufferfish
- [ ] Nether-exclusive rewards
- [ ] Higher baseline rewards than overworld

### Nether Features
- [ ] Bastion fishing spots
- [ ] Fortress fishing spots
- [ ] Soul Sand Valley special fish
- [ ] Crimson/Warped forest varieties

**Estimated Completion:** 2 weeks

---

## 🐙 Phase 10: Boss Fish (Major Update)

**Focus:** Epic multiplayer encounters

### Cthulhu Boss Event
- [ ] Quarterly spawn system
- [ ] Multiplayer requirement (3+ players)
- [ ] Boss health bar
- [ ] Attack phases
- [ ] Damage tracking per player
- [ ] Loot distribution system
- [ ] Friend bonus (+5% damage, better loot)

### ModelEngine Integration
- [ ] Custom 3D Cthulhu model
- [ ] Boss animations
- [ ] Particle effects
- [ ] Sound effects
- [ ] Spawn animations

### Boss Mechanics
- [ ] Phase 1: Tentacle attacks
- [ ] Phase 2: Summon minions
- [ ] Phase 3: Enrage mode
- [ ] Loot tiers based on contribution
- [ ] Title rewards
- [ ] Unique Cthulhu fish drop

### Other Boss Fish (Future)
- [ ] Kraken (Ocean boss)
- [ ] Leviathan (Deep ocean boss)
- [ ] Phoenix Fish (Nether boss)
- [ ] Void Serpent (End boss)

**Estimated Completion:** 4-6 weeks (major update)

---

## 🎨 Phase 11: Polish & Optimization

**Focus:** Performance, UX, and quality of life

### Performance
- [ ] Database optimization
- [ ] Caching improvements
- [ ] Async operations for heavy tasks
- [ ] Memory leak fixes

### QOL Features
- [ ] Fishing statistics
- [ ] Personal bests tracking
- [ ] Fish caught timeline
- [ ] Achievements system
- [ ] Cosmetic titles
- [ ] Chat formatting improvements

### Admin Tools
- [ ] Fish spawn tester
- [ ] Debug commands
- [ ] Performance metrics
- [ ] Database backup/restore GUI

### Documentation
- [ ] Complete GitBook documentation
- [ ] Video tutorials
- [ ] API documentation
- [ ] Config examples

**Estimated Completion:** 2-3 weeks

---

## 🔮 Future Considerations (Phase 12+)

These are ideas being explored but not yet scheduled:

### Fishing Minigames
- Quick-time events for rare fish
- Button mashing for big fish
- Timing-based hook system

### Fishing Competitions
- Daily challenges
- Weekly leaderboards
- Seasonal rankings
- Rewards shop

### Aquariums
- Display caught fish in tanks
- Breeding system
- Fish trading between players

### Fishing Lore
- Story-driven discoveries
- Hidden legendary fish
- Quest chains
- Fishing journal

### Resource Pack Integration
- Custom fish textures
- Custom rod models
- Particle effects
- Sound replacements

### Additional Integrations
- Discord webhooks for rare catches
- PlaceholderAPI expansions
- WorldGuard region bonuses
- MythicMobs fishing mobs

---

## 📊 Community Requested Features

Based on staff feedback:

- [x] No trash loot (completed)
- [ ] Party fishing (Phase 5)
- [ ] Weather/storm buffs (Phase 4)
- [ ] Depth system (Phase 4)
- [ ] Boat fishing bonus (Phase 4)
- [ ] Nether fishing (Phase 9)
- [ ] Cthulhu boss (Phase 10)
- [ ] Random server events (Phase 6)
- [ ] Skill tree expansion (Phase 7)
- [ ] No codex-gated buffs (design philosophy - permanent)

---

## 📝 Notes

* Timeline estimates are approximate
* Phases may be reordered based on community feedback
* Bug fixes and hotfixes released as needed
* Major versions will be announced in advance

**Want to influence the roadmap?** Join our Discord and share your ideas!

---

*Last Updated: February 24, 2026*
