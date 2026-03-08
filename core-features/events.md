# Dynamic Events

Dynamic Events are server-wide fishing bonuses that an admin can start on demand. When an event is active, all players benefit from enhanced fishing rewards.

## Event Types

There are three event types:

### FISHING_FRENZY

A general fishing boost that increases both XP and essence rewards.

| Multiplier | Value |
|------------|-------|
| XP | 2.0× |
| Essence | 1.5× |

Use this event to give all players a strong progression boost.

### RARE_TIDE

Increases the effective spawn weight of SAPPHIRE, RUBY, and AMETHYST fish.

| Multiplier | Value |
|------------|-------|
| Weight for SAPPHIRE+ | 2.5× |

Use this event when you want players to catch more rare fish.

### ESSENCE_SURGE

Doubles essence from all fishing.

| Multiplier | Value |
|------------|-------|
| Essence | 2.0× |

Use this event when players need essence for skill upgrades.

## Admin Commands

| Command | Description |
|---------|-------------|
| `/fish event start <TYPE> <minutes>` | Start an event of the given type for the given duration |
| `/fish event stop` | Stop the currently active event immediately |
| `/fish event info` | Check which event (if any) is currently active |

**Permission:** `swagfishing.event.manage` (required for start/stop; info is open to all)

**Valid TYPE values:** `FISHING_FRENZY`, `RARE_TIDE`, `ESSENCE_SURGE`

**Example:**
```
/fish event start FISHING_FRENZY 30
```
Starts a Fishing Frenzy for 30 minutes.

## Announcements

When an event starts and ends, a message is broadcast to all online players. Players always know when an event is active.

## Persistence

Events are **not** saved between server restarts. If the server restarts while an event is active, the event ends. Only one event can be active at a time.

## Multiplier Stacking

Event multipliers stack multiplicatively with skills, totems, and bait:

```
finalXP = base × skillXp × totemXp × eventXp × baitXp
finalEssence = base × skillEssence × totemEssence × eventEssence × baitEssence
```

A player with max XP Boost skill (1.5×), an XP Multiplier totem (1.25×), and during Fishing Frenzy (2.0×) would receive:

```
base × 1.5 × 1.25 × 2.0 = base × 3.75
```

## Configuration

Event multipliers are configurable in `config.yml`:

```yaml
events:
  multipliers:
    fishing-frenzy-xp: 2.0
    fishing-frenzy-essence: 1.5
    rare-tide: 2.5
    essence-surge: 2.0
```

## Related Features

* [Admin Commands](../server-owners/admin-commands.md) — full admin command reference
* [Permissions](../server-owners/permissions.md) — permission nodes
* [Skill Tree](../progression/skill-tree.md) — skills that stack with events
* [Totems](../progression/totems.md) — totems that stack with events
* [Bait](../progression/bait.md) — bait that stacks with events
