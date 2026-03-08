# Quick Start

Get up and fishing in 5 minutes.

## Prerequisites

* SwagFishing installed ([Installation Guide](installation.md))
* Server started with no console errors from SwagFishing

---

## Step 1: Start the Server

Start your server normally. Check the console for:

```
[SwagFishing] Loaded X fish from fish.yml
[SwagFishing] Loaded X fish from custom_fish.yml
[SwagFishing] Web Editor Started! http://your-ip:8080
```

If you see errors instead, check the [Installation Guide](installation.md).

---

## Step 2: Join and Grab a Rod

Join the server and grab any fishing rod from your inventory. No special rods are required — SwagFishing works with all vanilla rods.

---

## Step 3: Find Water and Fish

Head to any body of water (ocean, river, lake — anywhere). Cast your line and wait for a bite.

When you reel in:
* **85% chance:** You catch a custom SwagFishing fish
* **15% chance:** You get vanilla fishing loot

You'll see a colored catch message:

```
SwagFish » You caught a Common Cod!
```

Fish color corresponds to rarity: white = Quartz, green = Emerald, blue = Sapphire, red = Ruby, purple = Amethyst.

---

## Step 4: Check the Fish Codex

Open your collection to see which fish you've discovered:

```
/fish codex
```

The Codex shows all fish in the game, whether you've caught each one, and your overall completion percentage.

---

## Step 5: Open the Main Menu

```
/fish
```

From here you can access:
* **Fish Bag** — your stored fish
* **Sell Shop** — sell fish for money
* **Gutting** — convert fish to essence
* **Skill Tree** — upgrade your passive abilities
* **Totems** — equip fishing buffs
* **Bait** — manage consumable boosts

---

## Step 6: Check Your Stats

```
/fish stats
```

This shows your current fishing level, XP, essence balance, fish caught, and money earned.

---

## Step 7: Upgrade Your Skills

Once you've leveled up a few times and earned some skill points:

```
/fish skills
```

Start with **XP Boost** or **Essence Boost** to accelerate your progression. Each level costs 1 skill point + essence.

---

## Step 8: Access the Web Editor (Admins)

If you're a server admin, create custom fish through the web editor:

```
/fish web
```

This shows the clickable URL and current password. Open it in a browser, log in, and start creating fish visually.

Full guide: [Web Editor](../server-owners/web-editor.md)

---

## What's Next?

| Topic | Link |
|-------|------|
| Understanding fish spawns | [Fishing System](../core-features/fishing-system.md) |
| Managing your fish | [Fish Bag](../core-features/fish-bag.md) |
| Selling and gutting | [Selling Fish](../core-features/selling-fish.md) |
| Skill progression | [Skill Tree](../progression/skill-tree.md) |
| Totems | [Totems](../progression/totems.md) |
| Bait | [Bait](../progression/bait.md) |
| Server events | [Dynamic Events](../core-features/events.md) |
| Creating custom fish | [Web Editor](../server-owners/web-editor.md) |
| Full config reference | [Configuration](configuration.md) |
