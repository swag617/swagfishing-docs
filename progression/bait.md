# Bait

Bait items are consumable fishing boosts with a limited number of uses. Activate bait to temporarily increase XP, essence, rare fish chance, or sell prices until the uses run out.

## Opening the Bait GUI

```
/fish bait
```

Permission: `swagfishing.bait` (default: all players)

## How Bait Works

1. **Obtain bait** (from admins, deliveries, or other sources)
2. **Open the Bait GUI** and click a bait in your inventory section to activate it
3. The bait moves to the active section and its uses begin counting down on each catch
4. When uses reach 0, the bait is automatically removed
5. **Click an active bait** to deactivate it (remaining uses are discarded)

All active baits apply simultaneously on every catch. You can have multiple baits active at once (up to `bait.max-stacked-baits`).

## GUI Layout

| Area | Slots | Purpose |
|------|-------|---------|
| Inventory section | 10-16, 19-25 | Bait you own but haven't activated |
| Active section | 29-33 | Currently active baits |
| Info | 49 | Current active bait count and max |
| Close | 45 | Close the GUI |

## Bait Tiers

### Common

| ID | Effect | Notes |
|----|--------|-------|
| `worm_bait` | XP_BOOST | Minor XP increase |
| `crystal_dust` | ESSENCE_BOOST | Minor essence increase |
| `copper_lure` | RARE_BOOST | Minor weight boost for SAPPHIRE+ |

### Uncommon

| ID | Effect | Notes |
|----|--------|-------|
| `enhanced_worm` | XP_BOOST | Moderate XP increase |
| `prismarine_bait` | ESSENCE_BOOST | Moderate essence increase |
| `amethyst_lure` | RARE_BOOST | Moderate weight boost for SAPPHIRE+ |
| `golden_bait` | SELL_BOOST | Moderate sell price increase |

### Rare

| ID | Effect | Notes |
|----|--------|-------|
| `power_bait` | XP_BOOST | Strong XP increase |
| `surge_bait` | ESSENCE_BOOST | Strong essence increase |
| `deep_lure` | RARE_BOOST | Strong weight boost for SAPPHIRE+ |
| `market_bait` | SELL_BOOST | Strong sell price increase |

### Legendary

| ID | Effect | Notes |
|----|--------|-------|
| `radiant_extract` | XP_BOOST | Powerful XP increase |
| `essence_crystal` | ESSENCE_BOOST | Powerful essence increase |
| `master_lure` | RARE_BOOST | Powerful weight boost for SAPPHIRE+ |
| `fortune_bait` | SELL_BOOST | Powerful sell price increase |

## Effect Types

| Type | What It Boosts |
|------|---------------|
| `XP_BOOST` | XP received per catch |
| `ESSENCE_BOOST` | Essence received per catch |
| `RARE_BOOST` | Effective spawn weight for SAPPHIRE+ fish |
| `SELL_BOOST` | Sell price when selling fish |

## Multiplier Stacking

Bait effects stack multiplicatively with skills, totems, and events:

```
finalXP = base × skillXp × totemXp × eventXp × baitXp
finalEssence = base × skillEssence × totemEssence × eventEssence × baitEssence
```

Multiple active baits also multiply together. For example, two XP_BOOST baits with 1.2× and 1.3× multipliers give:

```
combined XP multiplier = 1.2 × 1.3 = 1.56×
```

## Persistence

Bait state (inventory and active baits including remaining uses) is saved to the database. Logging out and back in does not reset your bait.

## Configuration

```yaml
bait:
  max-stacked-baits: 3  # Max active baits at once
```

## Admin: Giving Bait

Admins can give bait to players:

```
/fish admin givebait <player> <baitId> <amount>
```

Permission: `swagfishing.admin`

**Valid bait IDs:** `worm_bait`, `crystal_dust`, `copper_lure`, `enhanced_worm`, `prismarine_bait`, `amethyst_lure`, `golden_bait`, `power_bait`, `surge_bait`, `deep_lure`, `market_bait`, `radiant_extract`, `essence_crystal`, `master_lure`, `fortune_bait`

## Related Features

* [Skill Tree](skill-tree.md) — skills that stack with bait
* [Totems](totems.md) — totems that stack with bait
* [Dynamic Events](../core-features/events.md) — events that stack with bait
* [Admin Commands](../server-owners/admin-commands.md) — givebait command reference
