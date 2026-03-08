# Lore Schemes

Lore Schemes are templates that automatically generate fish lore from placeholders. Instead of writing custom lore for every fish, you define a scheme once and let it populate the lore automatically.

## How It Works

When a fish has an empty `lore` field, SwagFishing applies that fish's rarity default scheme. The scheme template is filled in with the fish's actual stats and the result becomes the item's lore.

If you add custom lore lines to a fish, the scheme is bypassed entirely for that fish.

## Built-in Schemes

There are 5 built-in schemes, one per rarity:

| Scheme ID | Applies To |
|-----------|-----------|
| `default_quartz` | QUARTZ fish with empty lore |
| `default_emerald` | EMERALD fish with empty lore |
| `default_sapphire` | SAPPHIRE fish with empty lore |
| `default_ruby` | RUBY fish with empty lore |
| `default_amethyst` | AMETHYST fish with empty lore |

Built-in schemes are **read-only**. You cannot edit or delete them directly. Clone them through the web editor to create a customizable copy.

## Placeholders

Use these placeholders in scheme templates. They are replaced with the fish's actual values at runtime.

| Placeholder | Value |
|-------------|-------|
| `{displayName}` | Fish display name (with color codes) |
| `{description}` | Fish description |
| `{rarity}` | Rarity name (e.g., SAPPHIRE) |
| `{biomes}` | Comma-separated biome list |
| `{time}` | Time requirement (e.g., NIGHT) |
| `{weather}` | Weather requirement (e.g., RAIN) |
| `{xp}` | XP reward value |
| `{essence}` | Essence reward value |
| `{sellPrice}` | Sell price value |
| `{guttingEssence}` | Gutting essence value |
| `{minSize}` | Minimum size |
| `{maxSize}` | Maximum size |
| `{minYLevel}` | Minimum Y-level |
| `{maxYLevel}` | Maximum Y-level |

## Custom Schemes

Custom schemes are stored in `plugins/SwagFishing/custom_schemes.yml`.

### Example Scheme YAML

```yaml
my_custom_scheme:
  lines:
    - "&7{description}"
    - ""
    - "&8Rarity: &r{rarity}"
    - "&8Biomes: &7{biomes}"
    - "&8Active: &7{time} | {weather}"
    - ""
    - "&eXP: &f{xp}   &bEssence: &f{essence}"
    - "&aValue: &f${sellPrice}"
    - "&6Gutting: &f{guttingEssence} essence"
    - ""
    - "&8Size: &7{minSize} - {maxSize}"
```

Each entry in `lines` is one line of lore. Empty strings produce blank lines.

## Managing Schemes in the Web Editor

The **Schemes tab** in the Web Editor is the easiest way to manage schemes.

### Viewing Built-in Schemes

1. Open the web editor and go to the Schemes tab
2. Built-in schemes are listed and can be previewed but not edited

### Creating a Custom Scheme

1. Click "Create New Scheme"
2. Give it a unique ID
3. Add lore lines using placeholders
4. Click Save

Or clone a built-in scheme:
1. Click "Clone" on a built-in scheme
2. A new custom scheme is created with the same content
3. Edit the clone and save it

### Applying a Scheme to Fish

There are two approaches:

**Auto-apply via empty lore:** Leave the fish's lore list empty. The rarity default scheme applies automatically. To use a custom scheme instead of the rarity default, you would need to either modify the rarity default or add the scheme's output as static lore lines.

**Apply in web editor:** In the fish editor form, use the scheme selector to apply a scheme template to the lore field.

## Manual YAML

You can also edit `custom_schemes.yml` directly:

```yaml
scheme_id:
  lines:
    - "Line 1"
    - "Line 2"
```

After editing, run `/fish reload` to apply.

## Related Features

* [Web Editor](web-editor.md) — Schemes tab documentation
* [Creating Custom Fish](creating-fish.md) — how to set fish lore
