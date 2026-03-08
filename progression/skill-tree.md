# Skill Tree

The Skill Tree is SwagFishing's passive progression system. Spend skill points and essence to permanently upgrade your fishing abilities.

## Opening the Skill Tree

```
/fish skills
```

Permission: `swagfishing.skills` (default: all players)

## GUI Layout

The Skill Tree uses a 54-slot inventory:

| Slot | Item |
|------|------|
| 11 | XP Boost skill |
| 13 | Essence Boost skill |
| 15 | Rare Finder skill |
| 29 | Market Expert skill |
| 31 | Lucky Cast skill |
| 33 | Delivery Expert skill |
| 45 | Close button |
| 49 | Info / help |

Each skill item shows its current level, max level, cost to upgrade, and current effect.

**Item color indicates status:**
* Green name — can upgrade (have enough skill points and essence)
* Gray name — already at max level
* Red name — cannot afford the upgrade

## Skills

| ID | Name | Max Level | Cost (per level) | Effect |
|----|------|-----------|-----------------|--------|
| `xp_boost` | XP Boost | 5 | 50 essence | +10% XP per level |
| `essence_boost` | Essence Boost | 5 | 50 essence | +10% essence per level |
| `rare_finder` | Rare Finder | 3 | 100 essence | ×1.5 / ×2.0 / ×3.0 weight for SAPPHIRE+ fish |
| `sell_boost` | Market Expert | 3 | 75 essence | +10% sell price per level |
| `lucky_cast` | Lucky Cast | 3 | 150 essence | +5% custom-fish-chance per level |
| `delivery_bonus` | Delivery Expert | 2 | 200 essence | +25% delivery essence per level |

Each upgrade costs **1 skill point** plus the listed essence amount.

## Upgrading Skills

1. Open the Skill Tree with `/fish skills`
2. Click a skill to upgrade it (if you can afford it)
3. The skill levels up and the costs are deducted

Skill points are earned by leveling up (see [Leveling & XP](leveling.md)).

## Refunding Skills

If `skills.allow-refunds` is enabled in config (default: true), you can get a partial refund:

1. **Shift-click** a skill in the Skill Tree
2. The skill level decreases by 1
3. You receive back the skill point and a percentage of the essence cost (`skills.refund-cost-percentage`, default 50%)

```yaml
skills:
  allow-refunds: true
  refund-cost-percentage: 50  # Returns 50% of essence cost
```

## Multiplier Stacking

Skill effects stack multiplicatively with totems, events, and bait:

```
finalXP = base × skillXp × totemXp × eventXp × baitXp
finalEssence = base × skillEssence × totemEssence × eventEssence × baitEssence
```

### XP Boost at max level (5):
1.0 + (5 × 0.10) = **1.5×** XP

### Essence Boost at max level (5):
1.0 + (5 × 0.10) = **1.5×** essence

### Rare Finder effects:
* Level 1: ×1.5 weight for SAPPHIRE+ fish
* Level 2: ×2.0 weight for SAPPHIRE+ fish
* Level 3: ×3.0 weight for SAPPHIRE+ fish

## Strategy Tips

* **New players:** Start with XP Boost or Essence Boost to accelerate all future progression
* **Rare hunters:** Rare Finder significantly increases the chance of catching SAPPHIRE, RUBY, and AMETHYST fish
* **Economy focus:** Market Expert increases all sell prices, compounding with Sell Shop earnings
* **Delivery runners:** Delivery Expert is the only skill that boosts delivery rewards — worth 2 levels early
* Refunding is cheap (costs only 50% of the essence) so don't be afraid to experiment

## Related Features

* [Leveling & XP](leveling.md) — how to earn skill points
* [Totems](totems.md) — equip buffs that stack with skills
* [Bait](bait.md) — consumable boosts that stack with skills
* [Dynamic Events](../core-features/events.md) — server events that stack with skills
