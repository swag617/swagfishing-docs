# Creating Custom Fish

Custom fish can be created two ways: through the **Web Editor** (recommended) or by editing YAML files directly.

## Method 1: Web Editor (Recommended)

The Web Editor provides a visual form with a live Minecraft-style preview. No YAML knowledge required.

1. Open the web editor URL (run `/fish web` in-game to see the URL)
2. Log in with your password
3. Click "Create New Fish"
4. Fill in the form
5. Click "Save Fish"
6. Run `/fish reload` in-game

Full guide: [Web Editor](web-editor.md)

---

## Method 2: Manual YAML

Custom fish are defined in `plugins/SwagFishing/custom_fish.yml`. Base fish (read-only) are in `fish.yml`.

### Full Field Reference

```yaml
your_fish_id:
  displayName: "&bYour Fish Name"
  rarity: SAPPHIRE
  material: COD
  customModelData: 0
  description: "A beautiful fish from the deep ocean."

  biomes:
    - OCEAN
    - DEEP_OCEAN

  time: ANY          # ANY, DAY, NIGHT, DAWN, DUSK
  weather: ANY       # ANY, CLEAR, RAIN, THUNDER

  minYLevel: -64
  maxYLevel: 320

  worlds:
    - world

  regions: []         # WorldGuard regions (optional)

  weight: 20

  xpReward: 40
  essenceReward: 15
  sellPrice: 175.0
  guttingEssence: 22

  minSize: 0.5
  maxSize: 3.0

  lore: []            # Leave empty to use rarity default scheme

  catchCommands: []   # Commands run on catch
```

### Field Descriptions

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `displayName` | String | Yes | Player-visible name with color codes |
| `rarity` | Enum | Yes | QUARTZ, EMERALD, SAPPHIRE, RUBY, or AMETHYST |
| `material` | String | Yes | Minecraft item material (COD, SALMON, TROPICAL_FISH, PUFFERFISH, etc.) |
| `customModelData` | Int | No | Custom model data for resource packs (0 = none) |
| `description` | String | No | Flavor text displayed in lore |
| `biomes` | List | No | Minecraft biome names. Empty = all biomes |
| `time` | Enum | Yes | ANY, DAY, NIGHT, DAWN, or DUSK |
| `weather` | Enum | Yes | ANY, CLEAR, RAIN, or THUNDER |
| `minYLevel` | Int | No | Minimum Y-level for this fish to spawn |
| `maxYLevel` | Int | No | Maximum Y-level for this fish to spawn |
| `worlds` | List | No | World names. Empty = all worlds |
| `regions` | List | No | WorldGuard region names. Empty = all regions |
| `weight` | Int | Yes | Spawn weight relative to other eligible fish |
| `xpReward` | Int | Yes | XP granted on catch |
| `essenceReward` | Int | Yes | Essence granted on catch |
| `sellPrice` | Double | Yes | Money value when sold (requires Vault; 0 = not sellable) |
| `guttingEssence` | Int | Yes | Essence granted when gutted |
| `minSize` | Double | No | Minimum fish size (cosmetic) |
| `maxSize` | Double | No | Maximum fish size (cosmetic) |
| `lore` | List | No | Custom lore lines. Leave empty to use the rarity default scheme |
| `catchCommands` | List | No | Commands run when this fish is caught |

### Color Codes

```
&0-&9, &a-&f  — Legacy Minecraft colors
&#RRGGBB       — Hex color
<#RRGGBB>      — Adventure format hex
&l             — Bold
&o             — Italic
&n             — Underline
&m             — Strikethrough
&r             — Reset
```

### Catch Command Placeholders

```
{player}   — Player name
{fish}     — Fish name (no color codes)
{rarity}   — Rarity name
```

---

## Example Fish

### Quartz Example

```yaml
river_minnow:
  displayName: "&fRiver Minnow"
  rarity: QUARTZ
  material: COD
  description: "A tiny fish common in rivers."
  biomes:
    - RIVER
    - FROZEN_RIVER
  time: ANY
  weather: ANY
  weight: 90
  xpReward: 5
  essenceReward: 2
  sellPrice: 10.0
  guttingEssence: 3
  minSize: 0.1
  maxSize: 0.5
  lore: []
  catchCommands: []
```

### Sapphire Example

```yaml
midnight_eel:
  displayName: "&9Midnight Eel"
  rarity: SAPPHIRE
  material: COD
  description: "Only emerges from deep ocean trenches at night."
  biomes:
    - DEEP_OCEAN
    - DEEP_COLD_OCEAN
    - DEEP_LUKEWARM_OCEAN
  time: NIGHT
  weather: ANY
  minYLevel: -64
  maxYLevel: 30
  weight: 20
  xpReward: 40
  essenceReward: 15
  sellPrice: 175.0
  guttingEssence: 22
  minSize: 1.5
  maxSize: 4.0
  lore: []
  catchCommands: []
```

### Amethyst Example

```yaml
celestial_koi:
  displayName: "&5&lCelestial Koi"
  rarity: AMETHYST
  material: TROPICAL_FISH
  description: "An ethereal fish said to bring fortune."
  biomes:
    - OCEAN
    - RIVER
    - LAKE
  time: DAWN
  weather: CLEAR
  weight: 2
  xpReward: 275
  essenceReward: 110
  sellPrice: 1200.0
  guttingEssence: 165
  minSize: 2.0
  maxSize: 5.0
  lore: []
  catchCommands:
    - "broadcast &5&l✦ {player} has captured the legendary {fish}!"
```

---

## Reward Balancing Guidelines

| Rarity | XP | Essence | Price | Gutting Essence |
|--------|----|---------|-------|----------------|
| Quartz | 5-10 | 2-3 | $10-20 | 3-5 |
| Emerald | 15-25 | 5-8 | $50-100 | 8-12 |
| Sapphire | 30-50 | 10-20 | $150-250 | 15-30 |
| Ruby | 75-150 | 30-50 | $400-750 | 45-75 |
| Amethyst | 200-500 | 100-200 | $1000-2000 | 150-300 |

## Weight Guidelines

| Rarity | Suggested Weight |
|--------|----------------|
| Quartz | 80-100 |
| Emerald | 40-60 |
| Sapphire | 20-35 |
| Ruby | 8-15 |
| Amethyst | 1-5 |

Weight is relative to other eligible fish in the same biome/time/weather conditions. A fish with weight 100 is twice as likely to appear as a fish with weight 50.

---

## Applying Changes

After editing `custom_fish.yml`, run:

```
/fish reload
```

Check the console for "Loaded X fish" to confirm the file was parsed correctly.

## Related Features

* [Web Editor](web-editor.md) — visual fish creation with live preview
* [Lore Schemes](schemes.md) — automatic lore templates for fish
