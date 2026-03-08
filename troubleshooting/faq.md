# Frequently Asked Questions

## Fishing

**Why am I not catching any custom fish?**

Check the following:
1. Confirm you're in the correct biome for your target fish (check the Fish Codex for biome requirements)
2. Check the time and weather requirements — some fish only spawn at night or in rain
3. Verify `fishing.custom-fish-chance` in config is set appropriately (default 0.85 = 85% chance)
4. Run `/fish reload` if you recently made config changes

---

**Can I fish anywhere?**

Yes, you can fish in any body of water. However, the fish you can catch depend on your biome, Y-level, time of day, and weather. Check the Fish Codex to see what conditions each fish requires.

---

**Why are Ruby and Amethyst fish announced server-wide?**

This is intentional. Ruby and Amethyst fish are extremely rare, and the server-wide announcement celebrates the player's achievement and adds excitement for everyone online.

---

## Skill Tree

**Why can't I open the Skill Tree?**

You need the `swagfishing.skills` permission. This is granted to all players by default, but your server may have revoked it. Ask an admin to check your permissions.

---

**How do I get skill points?**

Skill points are earned by leveling up your fishing level. You receive at least 1 skill point per level, with bonus skill points at milestone levels (10, 25, 50, 100 by default). Check `/fish stats` to see your current skill points.

---

**What does essence do?**

Essence is used to upgrade skills in the Skill Tree. Each skill level costs a fixed amount of essence plus 1 skill point. You earn essence by catching fish, gutting fish, and completing deliveries.

---

**How do I refund a skill?**

Shift-click a skill in the Skill Tree GUI. This refunds the skill point and returns a percentage of the essence cost (default 50%). Refunds must be enabled in config (`skills.allow-refunds: true`).

---

## Bait & Totems

**Does bait persist when I log off?**

Yes. Bait state (both your inventory and active baits, including remaining uses) is saved to the database. You pick up exactly where you left off when you log back in.

---

**What happens to active bait when the server restarts?**

Active bait with remaining uses is preserved — it is saved to the database and restored when you next join.

---

## Web Editor

**Why is the web editor on port 8080 by default?**

SwagFishing runs a built-in HTTP server to host the web editor. Port 8080 is a common alternative HTTP port. You can change it in `config.yml` under `web-editor.port`. Changes to the port require a full server restart.

---

## General

**What is essence used for exactly?**

Essence is SwagFishing's progression currency. It's used to upgrade skills in the Skill Tree (along with skill points). You earn it from catching fish, gutting fish, and completing deliveries. The Delivery Expert and Essence Boost skills increase how much you earn.

---

**I changed config.yml — do I need to restart?**

No. Run `/fish reload` to apply changes to config and fish data. The only exception is changes to `web-editor.port` or `web-editor.bind-address`, which require a full server restart.

---

**Where are my fish stored?**

Caught fish go to your Fish Bag automatically (if `fish-bag.auto-add: true` in config). Fish in the bag are stored in the SQLite database at `plugins/SwagFishing/fishing.db`.

---

**Need more help?**

See the [Support](support.md) page.
