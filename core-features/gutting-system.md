# Gutting System

Gutting converts fish from your Fish Bag into essence. It typically yields more essence than catching the fish directly, making it a key part of the essence economy.

## Opening the Gutting GUI

```
/fish gut
```

## What Is Gutting?

Gutting is an alternative to selling fish. Instead of converting fish to money, you convert them to **essence** — the currency used to upgrade your [Skill Tree](../progression/skill-tree.md).

The gutting essence reward is calculated from the fish's base essence value, multiplied by the gutting multiplier in config (default 1.5×). This means gutting consistently yields more essence than just catching the fish normally.

## GUI Layout

The Gutting GUI uses a 54-slot inventory:

| Area | Slots | Purpose |
|------|-------|---------|
| Input slots | 10-16, 19-25, 28-34 | Place fish here to gut them |
| Confirm button | Slot 40 | Shows essence preview; click to confirm gutting |

### Using the GUI

1. Open the Gutting GUI with `/fish gut`
2. Place fish into the input slots (they are pulled from your Fish Bag)
3. The Confirm button updates to show how much essence you'll receive
4. Click Confirm to gut all placed fish and receive the essence

## Essence Calculation

```
guttingEssence = fish.guttingEssence × essence.gutting-multiplier
```

For example, a fish with 10 base gutting essence and the default 1.5× multiplier yields 15 essence when gutted.

The gutting essence value per fish is set in the fish definition (see [Creating Custom Fish](../server-owners/creating-fish.md)).

## Bulk Gutting

The input area holds up to 21 fish at once (slots 10-16, 19-25, 28-34). You can fill all slots and confirm in one click to gut multiple fish simultaneously.

## Configuration

```yaml
essence:
  gutting-multiplier: 1.5  # Multiplier applied to fish gutting essence value
```

Increase this value to make gutting more profitable relative to the fish's base essence.

## Related Features

* [Fish Bag](fish-bag.md) — fish are pulled from here when you gut
* [Selling Fish](selling-fish.md) — alternative to gutting if you want money instead of essence
* [Skill Tree](../progression/skill-tree.md) — essence is used to upgrade skills
