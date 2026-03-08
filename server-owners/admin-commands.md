# Admin Commands

This page covers all commands that require elevated permissions to use.

> **Note:** All commands use `/fish` as the primary command. `/fish` is an alias for `/swagfish` — both work identically.

## Command Reference

| Command | Permission | Description |
|---------|-----------|-------------|
| `/fish reload` | `swagfishing.admin` | Reload config.yml, fish, and schemes without restarting |
| `/fish web` | `swagfishing.admin` | Display web editor URL and current password |
| `/fish event start <TYPE> <minutes>` | `swagfishing.event.manage` | Start a server-wide fishing event |
| `/fish event stop` | `swagfishing.event.manage` | Stop the currently active event |
| `/fish event info` | *(open to all)* | Display the currently active event (if any) |
| `/fish givetotem <player> <totemId>` | `swagfishing.givetotem` | Give a totem to a player |
| `/fish admin givebait <player> <baitId> <amount>` | `swagfishing.admin` | Give bait items to a player |
| `/fish top` | *(open to all)* | Show the fishing leaderboard |

## Event Commands

### Starting an Event

```
/fish event start <TYPE> <minutes>
```

**Valid TYPE values:**

| Type | Effect |
|------|--------|
| `FISHING_FRENZY` | 2.0× XP + 1.5× essence for all players |
| `RARE_TIDE` | 2.5× spawn weight for SAPPHIRE+ fish |
| `ESSENCE_SURGE` | 2.0× essence for all players |

**Example:**
```
/fish event start RARE_TIDE 60
```
Starts a Rare Tide event lasting 60 minutes.

### Stopping an Event

```
/fish event stop
```

Ends the active event immediately. A server-wide message is broadcast.

### Checking Event Status

```
/fish event info
```

Shows which event (if any) is active and the time remaining.

### Notes

* Only one event can be active at a time
* Events end automatically when the timer expires
* Events do not persist through server restarts

## Totem Commands

### Give Totem

```
/fish givetotem <player> <totemId>
```

**Valid totem IDs:**

| Totem ID | Effect |
|----------|--------|
| `basic_luck` | 1.2× rarity weight for SAPPHIRE+ |
| `advanced_luck` | 1.5× rarity weight for SAPPHIRE+ |
| `essence_boost` | 1.25× essence |
| `xp_multiplier` | 1.25× XP |
| `rare_finder` | 2.0× rarity weight for SAPPHIRE+ |
| `speed_caster` | 1.1× XP + 1.1× essence |
| `weather_control` | 1.5× rarity weight for SAPPHIRE+ (rain only) |
| `ocean_master` | 1.5× XP + 1.5× essence |
| `legendary_aura` | 3.0× rarity weight for RUBY+ |
| `ultimate_fisher` | 2.0× XP + 2.0× essence + 2.0× rarity for SAPPHIRE+ |

**Example:**
```
/fish givetotem Steve legendary_aura
```

## Bait Commands

### Give Bait

```
/fish admin givebait <player> <baitId> <amount>
```

**Valid bait IDs:**

| Tier | Bait IDs |
|------|---------|
| Common | `worm_bait`, `crystal_dust`, `copper_lure` |
| Uncommon | `enhanced_worm`, `prismarine_bait`, `amethyst_lure`, `golden_bait` |
| Rare | `power_bait`, `surge_bait`, `deep_lure`, `market_bait` |
| Legendary | `radiant_extract`, `essence_crystal`, `master_lure`, `fortune_bait` |

**Example:**
```
/fish admin givebait Steve master_lure 5
```

## Reload

```
/fish reload
```

Reloads:
* `config.yml`
* `fish.yml`
* `custom_fish.yml`
* `schemes.yml`
* `custom_schemes.yml`

Does **not** require a server restart. Note: changes to the web editor port or bind-address do require a full restart.

## Related Pages

* [Permissions](permissions.md) — all permission nodes
* [Dynamic Events](../core-features/events.md) — event documentation
* [Totems](../progression/totems.md) — totem documentation
* [Bait](../progression/bait.md) — bait documentation
