# Selling Fish

The Sell Shop lets you convert fish from your Fish Bag into money through a GUI interface.

## Opening the Sell Shop

```
/fish shop
```

or

```
/fish sell
```

Permission: `swagfishing.sell` (default: all players)

## Requirements

* **Vault** must be installed and a compatible economy plugin must be active
* Fish must be in your Fish Bag (not in your inventory)

## How It Works

The Sell Shop displays all fish in your bag that have a sell price greater than 0. Each fish card shows:

* Fish name (colored by rarity)
* Rarity tier
* Sell price

### Selling Individual Fish

Click any fish in the Sell Shop to sell that fish. The money is added to your economy balance immediately and the fish is removed from your bag.

### Sell All

Click the **Sell All** button (slot 47) to sell every fish currently visible in the shop. A confirmation step prevents accidental mass selling.

When you Sell All, the total amount earned is shown in chat.

## GUI Layout

| Slot | Item |
|------|------|
| Fish slots (paginated) | Fish from your bag with sell price > 0 |
| Slot 47 | Sell All button |
| Slot 49 | Info / help |
| Slot 45 / 53 | Page navigation |

## Stats Tracking

Every sale updates your `totalMoneyEarned` stat, visible via `/fish stats`.

## Sell Price Multipliers

Your final sell price is affected by:

* **Market Expert skill** — +10% sell price per level (max 3 levels = +30%)
* **Market Bait / Fortune Bait** — SELL_BOOST bait type adds a multiplier while active

All multipliers stack multiplicatively.

## Related Features

* [Fish Bag](fish-bag.md) — where your fish are stored before selling
* [Gutting System](gutting-system.md) — alternative to selling: converts fish to essence instead
* [Skill Tree](../progression/skill-tree.md) — Market Expert skill for sell price bonuses
