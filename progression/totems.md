# Totems

Totems are persistent fishing buffs that you unlock by reaching a required fishing level. Equip them to passively boost your XP, essence, or rare fish chance while you fish.

## Opening the Totem GUI

```
/fish totems
```

Permission: `swagfishing.totems` (default: all players)

## How Totems Work

1. **Unlock** a totem by reaching the required fishing level
2. **Equip** unlocked totems (up to `max-equipped-totems` simultaneously)
3. While equipped, the totem's effect applies to every fish you catch

Totems do not expire or consume uses. They stay active until you unequip them.

## GUI Layout

| Slot | Item |
|------|------|
| 11-15, 29-33 | Totem entries |
| 45 | Close button |
| 49 | Equipped count and max |

**Item appearance indicates status:**
* NETHER_STAR — totem is unlocked and not equipped
* GOLDEN_APPLE — totem is currently equipped
* RED_GLASS_PANE — totem is locked; shows required fishing level in lore

Click an unlocked totem to equip it. Click an equipped totem to unequip it.

## All Totems

| ID | Effect | Notes |
|----|--------|-------|
| `basic_luck` | 1.2× rarity weight for SAPPHIRE+ fish | — |
| `advanced_luck` | 1.5× rarity weight for SAPPHIRE+ fish | — |
| `essence_boost` | 1.25× essence | — |
| `xp_multiplier` | 1.25× XP | — |
| `rare_finder` | 2.0× rarity weight for SAPPHIRE+ fish | — |
| `speed_caster` | 1.1× XP + 1.1× essence | — |
| `weather_control` | 1.5× rarity weight for SAPPHIRE+ fish | Rain only |
| `ocean_master` | 1.5× XP + 1.5× essence | — |
| `legendary_aura` | 3.0× rarity weight for RUBY+ fish | Affects RUBY and AMETHYST |
| `ultimate_fisher` | 2.0× XP + 2.0× essence + 2.0× rarity for SAPPHIRE+ | Most powerful totem |

## Unlock Levels

Unlock levels are configured in `config.yml` under `totems.unlock-levels`. Default values:

| Totem | Required Level |
|-------|---------------|
| basic_luck | 5 |
| essence_boost | 5 |
| xp_multiplier | 5 |
| speed_caster | 10 |
| advanced_luck | 15 |
| rare_finder | 20 |
| weather_control | 25 |
| ocean_master | 30 |
| legendary_aura | 40 |
| ultimate_fisher | 50 |

Admins can change these values in config to suit their server's progression pace.

## Max Equipped Totems

By default, players can equip up to **2 totems** simultaneously. Admins can change this:

```yaml
totems:
  max-equipped-totems: 2
```

Increasing this value allows players to stack more effects at once.

## Admin: Giving Totems

Admins can give totems directly to players:

```
/fish givetotem <player> <totemId>
```

Permission: `swagfishing.givetotem`

**Valid totem IDs:** `basic_luck`, `advanced_luck`, `essence_boost`, `xp_multiplier`, `rare_finder`, `speed_caster`, `weather_control`, `ocean_master`, `legendary_aura`, `ultimate_fisher`

## Multiplier Stacking

Totem effects stack multiplicatively with skills, events, and bait:

```
finalXP = base × skillXp × totemXp × eventXp × baitXp
finalEssence = base × skillEssence × totemEssence × eventEssence × baitEssence
```

Equipping multiple totems multiplies their effects together. For example, equipping `xp_multiplier` (1.25×) and `speed_caster` (1.1×):

```
combined XP multiplier = 1.25 × 1.1 = 1.375×
```

## Strategy Tips

* Early game: `xp_multiplier` and `essence_boost` accelerate all progression
* Rare hunting: `rare_finder` or `legendary_aura` dramatically increase rare fish chance
* Late game: `ultimate_fisher` is the strongest single totem — unlock it at level 50
* `weather_control` is situationally powerful — its 1.5× rare boost only applies when it's raining

## Related Features

* [Leveling & XP](leveling.md) — earn fishing levels to unlock totems
* [Skill Tree](skill-tree.md) — skills that stack with totems
* [Bait](bait.md) — consumable boosts that stack with totems
* [Admin Commands](../server-owners/admin-commands.md) — givetotem command reference
