# Configuration

SwagFishing uses a single `config.yml` file located at `plugins/SwagFishing/config.yml`. This page documents every configurable section.

After editing, run `/fish reload` to apply changes without restarting.

---

## Web Editor

```yaml
web-editor:
  enabled: true
  port: 8080
  bind-address: "0.0.0.0"
  password: "changeme"
```

| Key | Default | Description |
|-----|---------|-------------|
| `enabled` | `true` | Enable or disable the built-in HTTP server |
| `port` | `8080` | Port the web editor listens on |
| `bind-address` | `"0.0.0.0"` | Network interface to bind to. Use `"127.0.0.1"` for localhost only. |
| `password` | `"changeme"` | Password to access the web editor. **Change this immediately.** |

---

## Fishing

```yaml
fishing:
  enabled: true
  custom-fish-chance: 0.85

  rarity-weights:
    quartz: 1.0
    emerald: 0.5
    sapphire: 0.25
    ruby: 0.1
    amethyst: 0.05
```

| Key | Default | Description |
|-----|---------|-------------|
| `enabled` | `true` | Enable custom fishing. If false, vanilla fishing is unchanged. |
| `custom-fish-chance` | `0.85` | Probability (0.0–1.0) that a catch produces a custom fish instead of vanilla loot |
| `rarity-weights.quartz` | `1.0` | Weight multiplier applied to all QUARTZ fish |
| `rarity-weights.emerald` | `0.5` | Weight multiplier applied to all EMERALD fish |
| `rarity-weights.sapphire` | `0.25` | Weight multiplier applied to all SAPPHIRE fish |
| `rarity-weights.ruby` | `0.1` | Weight multiplier applied to all RUBY fish |
| `rarity-weights.amethyst` | `0.05` | Weight multiplier applied to all AMETHYST fish |

Rarity weights are applied on top of each fish's individual weight. Lower values make rarer fish harder to catch.

---

## Fish Bag

```yaml
fish-bag:
  auto-add: true
```

| Key | Default | Description |
|-----|---------|-------------|
| `auto-add` | `true` | Automatically add caught fish to the Fish Bag. If false, fish go to inventory instead. |

---

## Essence

```yaml
essence:
  gutting-multiplier: 1.5
```

| Key | Default | Description |
|-----|---------|-------------|
| `gutting-multiplier` | `1.5` | Multiplier applied to essence reward when gutting a fish, compared to the base essence value |

A multiplier of 1.5 means gutting gives 50% more essence than the fish's base essence reward.

---

## Leveling

```yaml
leveling:
  xp-per-level: 1000
  max-level: 100
  skill-points-per-level: 1

  bonus-skill-points:
    10: 2
    25: 3
    50: 5
    100: 10
```

| Key | Default | Description |
|-----|---------|-------------|
| `xp-per-level` | `1000` | XP required to advance one level (used by built-in leveling; ignored if FleaJobs handles levels) |
| `max-level` | `100` | Maximum fishing level |
| `skill-points-per-level` | `1` | Skill points awarded per level-up |
| `bonus-skill-points` | Map | Extra skill points awarded at specific level milestones. Key = level, value = bonus points |

---

## Skills

```yaml
skills:
  allow-refunds: true
  refund-cost-percentage: 50
```

| Key | Default | Description |
|-----|---------|-------------|
| `allow-refunds` | `true` | Allow players to refund skills by shift-clicking in the Skill Tree GUI |
| `refund-cost-percentage` | `50` | Percentage of the skill's essence cost returned on refund (0–100) |

---

## Totems

```yaml
totems:
  max-equipped-totems: 2

  unlock-levels:
    basic_luck: 5
    advanced_luck: 15
    essence_boost: 5
    xp_multiplier: 5
    rare_finder: 20
    speed_caster: 10
    weather_control: 25
    ocean_master: 30
    legendary_aura: 40
    ultimate_fisher: 50

  effects:
    basic_luck:
      rarity-boost: 1.2
      min-rarity: SAPPHIRE
    advanced_luck:
      rarity-boost: 1.5
      min-rarity: SAPPHIRE
    essence_boost:
      essence-multiplier: 1.25
    xp_multiplier:
      xp-multiplier: 1.25
    rare_finder:
      rarity-boost: 2.0
      min-rarity: SAPPHIRE
    speed_caster:
      xp-multiplier: 1.1
      essence-multiplier: 1.1
    weather_control:
      rarity-boost: 1.5
      min-rarity: SAPPHIRE
      weather-condition: RAIN
    ocean_master:
      xp-multiplier: 1.5
      essence-multiplier: 1.5
    legendary_aura:
      rarity-boost: 3.0
      min-rarity: RUBY
    ultimate_fisher:
      xp-multiplier: 2.0
      essence-multiplier: 2.0
      rarity-boost: 2.0
      min-rarity: SAPPHIRE
```

| Key | Description |
|-----|-------------|
| `max-equipped-totems` | How many totems a player can have equipped simultaneously |
| `unlock-levels.*` | Fishing level required to unlock each totem |
| `effects.*` | Per-totem multiplier configuration |

---

## Bait

```yaml
bait:
  max-stacked-baits: 3

  types:
    worm_bait:
      tier: COMMON
      effect: XP_BOOST
      multiplier: 1.1
      uses: 10
    # ... additional bait types follow the same structure
```

| Key | Description |
|-----|-------------|
| `max-stacked-baits` | Maximum number of baits that can be active simultaneously |
| `types.<id>.tier` | Bait tier: COMMON, UNCOMMON, RARE, or LEGENDARY |
| `types.<id>.effect` | Effect type: XP_BOOST, ESSENCE_BOOST, RARE_BOOST, or SELL_BOOST |
| `types.<id>.multiplier` | Multiplier value applied when the bait is active |
| `types.<id>.uses` | Number of catches before the bait is consumed |

---

## Events

```yaml
events:
  multipliers:
    fishing-frenzy-xp: 2.0
    fishing-frenzy-essence: 1.5
    rare-tide: 2.5
    essence-surge: 2.0
```

| Key | Default | Description |
|-----|---------|-------------|
| `multipliers.fishing-frenzy-xp` | `2.0` | XP multiplier during a FISHING_FRENZY event |
| `multipliers.fishing-frenzy-essence` | `1.5` | Essence multiplier during a FISHING_FRENZY event |
| `multipliers.rare-tide` | `2.5` | Weight multiplier for SAPPHIRE+ fish during a RARE_TIDE event |
| `multipliers.essence-surge` | `2.0` | Essence multiplier during an ESSENCE_SURGE event |

---

## Applying Changes

Run this command in-game after editing `config.yml`:

```
/fish reload
```

This reloads all config values and fish data without a server restart. Changes to the web editor port or bind address require a full restart to take effect.
