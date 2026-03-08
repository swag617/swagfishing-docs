# Permissions

All SwagFishing permission nodes are listed below.

## Permission Reference

| Permission | Default | Description |
|-----------|---------|-------------|
| `swagfishing.admin` | op | Full admin access: reload, web editor URL, givebait |
| `swagfishing.skills` | true | Open the Skill Tree GUI (`/fish skills`) |
| `swagfishing.totems` | true | Open the Totem GUI (`/fish totems`) |
| `swagfishing.bait` | true | Open the Bait GUI (`/fish bait`) |
| `swagfishing.event.manage` | op | Start and stop server events |
| `swagfishing.givetotem` | op | Give totems to players (`/fish givetotem`) |
| `swagfishing.sell` | true | Open the Sell Shop and sell fish |
| `swagfishing.codex` | true | Open the Fish Codex (`/fish codex`) |

## Default Values

* `true` — All players have this permission by default. Revoke it from groups that should not have access.
* `op` — Only server operators have this permission by default.

## Notes

* `/fish event info` is open to all players regardless of permissions
* `/fish top` (leaderboard) is open to all players
* `/fish stats` is open to all players
* `/fish bag`, `/fish gut`, and the main menu (`/fish`) require no special permissions beyond being a player

## Configuration via Permission Plugin

Use a permission plugin like LuckPerms to assign or revoke permissions:

```
# Give a group access to events
/lp group admin permission set swagfishing.event.manage true

# Revoke sell access from a group
/lp group default permission set swagfishing.sell false
```

## Related Pages

* [Admin Commands](admin-commands.md) — full admin command reference
