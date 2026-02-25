# Fishing System

SwagFishing completely replaces Minecraft's vanilla fishing with a rich, progression-based system featuring over 100 unique fish across 5 rarity tiers.

## How Fishing Works

### Basic Mechanics

1. **Equip a fishing rod** (any rod works)
2. **Cast your line** into water
3. **Wait for a bite** (normal fishing mechanics)
4. **Reel in** when you get a bite
5. **Receive a custom fish** (85% chance) or vanilla loot (15%)

> The chance to catch custom fish vs vanilla loot is configurable in `config.yml`

### What Determines Fish Spawns?

When you catch a fish, SwagFishing checks multiple conditions:

#### Location Requirements

**Biome**  
Fish can be restricted to specific biomes:
* Ocean fish → Ocean, Deep Ocean, Cold Ocean, etc.
* River fish → River, Frozen River
* Swamp fish → Swamp, Mangrove Swamp
* Jungle fish → Jungle, Bamboo Jungle

**Y-Level (Altitude)**  
Some fish only spawn at certain heights:
* Deep ocean fish → Y 0-40
* Surface fish → Y 60-80
* Mountain lake fish → Y 100+

**World**  
Fish can be limited to specific worlds:
* Overworld only
* Nether only (future feature)
* End only

#### Time Requirements

Fish can be active only during specific times:

**DAWN** - 0 to 2000 ticks (Sunrise period)  
**DAY** - 2000 to 10000 ticks (Daytime)  
**DUSK** - 10000 to 12000 ticks (Sunset period)  
**NIGHT** - 12000+ ticks (Nighttime)  
**ANY** - All times (No restriction)

**Example:** Emerald Trout only spawns at DAWN

#### Weather Requirements

Fish can require specific weather:

**CLEAR** - No rain or thunder  
**RAIN** - Raining  
**THUNDER** - Thunderstorm  
**ANY** - Any weather

**Example:** Jungle Piranha is more active during RAIN

#### Depth Requirements (Future)

Fish will spawn based on water depth:
* **Shallow (< 3 blocks)** - Common fish only
* **Medium (3-10 blocks)** - Common + Uncommon
* **Deep (10+ blocks)** - All rarities

## Rarity System

Fish come in 5 rarity tiers, each with increasing rewards:

### Quartz (Common)
* **Weight:** High (80-100)
* **Rewards:** 5-6 XP, 2 Essence, $8-15
* **Examples:** Common Cod, River Bass, Swamp Catfish

### Emerald (Uncommon)
* **Weight:** Medium (40-50)
* **Rewards:** 15-20 XP, 5-6 Essence, $50-70
* **Examples:** Emerald Trout, Ocean Guardian, Jungle Piranha

### Sapphire (Rare)
* **Weight:** Low (18-25)
* **Rewards:** 35-45 XP, 12-18 Essence, $150-200
* **Examples:** Sapphire Marlin, Frozen Pike, Midnight Eel

### Ruby (Very Rare)
* **Weight:** Very Low (8-10)
* **Rewards:** 75-100 XP, 30-40 Essence, $400-500
* **Broadcasts:** Server announcement when caught!
* **Examples:** Ruby Tuna, Crimson Shark

### Amethyst (Mythical)
* **Weight:** Extremely Low (2-3)
* **Rewards:** 250-300 XP, 100-125 Essence, $1000-1500
* **Broadcasts:** Epic server announcement!
* **Examples:** Amethyst Leviathan, Celestial Koi

## Weighted Spawning

Fish don't spawn with equal probability. The system uses a weighted random selection:

### How It Works

1. **Filter eligible fish** based on location, time, weather
2. **Calculate total weight** from all eligible fish
3. **Apply rarity multipliers** from config
4. **Random selection** weighted by fish rarity + individual weight

### Example Scenario

You're fishing in the **Ocean** during **Day** with **Clear** weather:

**Eligible Fish:**
* Common Cod (weight: 100, rarity: QUARTZ)
* Ocean Guardian (weight: 40, rarity: EMERALD)  
* Sapphire Marlin (weight: 25, rarity: SAPPHIRE)

**Rarity Weights** (from config):
* QUARTZ: 1.0
* EMERALD: 0.5
* SAPPHIRE: 0.25

**Effective Weights:**
* Common Cod: 100 × 1.0 = 100
* Ocean Guardian: 40 × 0.5 = 20
* Sapphire Marlin: 25 × 0.25 = 6.25

**Chances:**
* Common Cod: ~79%
* Ocean Guardian: ~16%
* Sapphire Marlin: ~5%

## Fish Rewards

When you catch a fish, you receive:

### Essence
A custom currency used for:
* Crafting totems
* Buying upgrades
* Special shop items

### Experience (XP)
Used for leveling up:
* **FleaJobs Integration:** XP goes to FISHER job
* **Built-in System:** XP tracks your fishing level

### Money (Vault)
If Vault is installed:
* Fish track their value
* Sell fish at the Sell Shop
* Money goes to your economy balance

### Fish Item
A beautiful custom item with:
* Colored name
* Rarity badge
* Auto-generated lore (tier, price, biomes, etc.)
* NBT data storing fish ID

## Catch Messages

When you catch a fish, you see:

```
SwagFish » You caught a [Rarity Color][Fish Name]!
```

**Examples:**
* `SwagFish » You caught a Common Cod!` (white)
* `SwagFish » You caught a Emerald Trout!` (green)
* `SwagFish » You caught a Ruby Tuna!` (red)

### Legendary Broadcasts

When someone catches a **Ruby** or **Amethyst** fish, the entire server sees:

**Ruby Example:**
```
⚡ PlayerName hooked a legendary Ruby Tuna!
```

**Amethyst Example:**
```
⚡ INCREDIBLE! PlayerName captured the Amethyst Leviathan!
```

## Environmental Bonuses (Future)

Fish catch rates will be affected by:

### Weather Bonuses
* **Rain:** +10% rare fish chance
* **Thunder:** +20% rare fish + 15% XP

### Boat Fishing
* **In Boat:** +10% catch rate (secret bonus!)

### Standing in Water
* **Feet in water:** +5% catch rate

### Depth Bonus
* **Deep water (10+ blocks):** Access to rare fish
* **Shallow water (< 3 blocks):** Common fish only

## Tips for Success

> **Pro Tips:**
> * Fish in the **correct biome** for target fish
> * Check **time and weather** requirements
> * **Deeper water** = better fish (future)
> * **Party fishing** with friends for bonuses (future)
> * Use **skills** to improve catch rates (future)

## Configuration

All fishing mechanics can be tuned in `config.yml`:

```yaml
fishing:
  enabled: true
  custom-fish-chance: 0.85  # 85% custom fish, 15% vanilla
  
  rarity-weights:
    quartz: 1.0    # Common
    emerald: 0.5   # Uncommon  
    sapphire: 0.25 # Rare
    ruby: 0.1      # Very Rare
    amethyst: 0.05 # Mythical
```