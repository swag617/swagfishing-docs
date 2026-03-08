# Leveling & XP

SwagFishing includes a fishing XP and leveling system that drives progression. Your fishing level determines which totems you can unlock and how many skill points you earn.

## How XP Works

Every time you catch a custom fish, you receive XP based on that fish's `xpReward` value. XP accumulates toward your next fishing level.

Your final XP per catch is calculated multiplicatively:

```
finalXP = base × skillXp × totemXp × eventXp × baitXp
```

Relevant multipliers:
* **XP Boost skill** — up to +50% XP (level 5)
* **XP Multiplier totem** — 1.25× XP
* **Ocean Master totem** — 1.5× XP
* **Ultimate Fisher totem** — 2.0× XP
* **FISHING_FRENZY event** — 2.0× XP
* **XP-boosting bait** — varies by tier

## FleaJobs Integration

If FleaJobs is installed on your server, SwagFishing integrates automatically:

* All fishing XP is sent to the **FISHER** job in FleaJobs
* Your fishing level is read from FleaJobs via `SwagFishing.getPlayerFishingLevel(Player)`
* The built-in leveling system is not used when FleaJobs is present

If FleaJobs is **not** installed, SwagFishing's built-in leveling system handles XP and levels.

## Built-in Leveling

Without FleaJobs, levels are tracked internally:

```yaml
leveling:
  xp-per-level: 1000   # XP required per level
  max-level: 100
```

Adjust `xp-per-level` to control how fast players level up.

## Skill Points

Skill points are the currency for upgrading skills in the [Skill Tree](skill-tree.md). You earn skill points when you level up.

```yaml
leveling:
  skill-points-per-level: 1   # Points earned per level

  bonus-skill-points:          # Extra points at milestone levels
    10: 2
    25: 3
    50: 5
    100: 10
```

At level 10 you receive 2 bonus skill points, at level 25 you receive 3 bonus points, and so on.

## Viewing Your Stats

```
/fish stats
```

Shows:
* Current fishing level
* Current XP and XP needed for next level
* Essence balance
* Total fish caught
* Total money earned

## Leaderboard

```
/fish top
```

Displays the top players by fishing level or total fish caught (server-wide leaderboard).

## Tips

* XP from deliveries and events can dramatically speed up leveling
* Use XP Boost skill and XP-boosting totems to maximize XP per catch
* During a FISHING_FRENZY event, XP is doubled — great time to grind levels
* Bonus skill points at milestone levels (10, 25, 50, 100) reward long-term play

## Related Features

* [Skill Tree](skill-tree.md) — spend skill points earned from leveling
* [Totems](totems.md) — unlock totems at specific fishing levels
* [Dynamic Events](../core-features/events.md) — events that boost XP gain
