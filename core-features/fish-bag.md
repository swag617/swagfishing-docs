# Fish Bag

The Fish Bag is your personal fish storage. Caught fish are automatically stored here and persist between sessions.

## Opening the Fish Bag

```
/fish bag
```

## How It Works

When you catch a custom fish, it is automatically added to your Fish Bag (if `fish-bag.auto-add` is enabled in config, which it is by default). The fish is saved to the database and stays in your bag until you withdraw or sell it.

If auto-add is disabled, fish go to your regular inventory instead.

## GUI Layout

The Fish Bag uses a 54-slot paginated GUI:

| Area | Slots | Purpose |
|------|-------|---------|
| Filter row | Row 0 (slots 0-8) | Filter fish by rarity |
| Fish slots | Slots 9-44 | Displays fish in your bag |
| Previous page | Slot 45 | Navigate to previous page |
| Filter button | Slot 49 | Cycle through rarity filters |
| Next page | Slot 53 | Navigate to next page |

## Withdrawing Fish

* **Left-click** a fish to withdraw 1 into your inventory
* **Shift-click** a fish to withdraw the full stack

Withdrawn fish appear as items in your inventory and can be used for other purposes.

## Filtering

Click the filter button (slot 49) or the filter row items to cycle through rarity filters:

* All Rarities
* Quartz only
* Emerald only
* Sapphire only
* Ruby only
* Amethyst only

## Persistence

Fish in your bag are saved to the SQLite database. They persist through:
* Logging out and back in
* Server restarts
* Plugin reloads

## Configuration

```yaml
fish-bag:
  auto-add: true  # Automatically add caught fish to the bag
```

Set `auto-add: false` if you want fish to go directly to player inventory instead.

## Related Features

* [Selling Fish](selling-fish.md) — sell fish from your bag for money
* [Gutting System](gutting-system.md) — convert fish from your bag into essence
