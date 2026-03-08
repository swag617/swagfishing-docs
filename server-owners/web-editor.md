# Web Editor

The SwagFishing Web Editor is a full-featured, user-friendly interface that lets server admins create and manage custom fish and lore schemes without touching YAML files.

## Overview

### What Can You Do?

* Create new fish with a visual form
* Edit existing custom fish
* Delete custom fish
* View all fish in a card grid with search, filter, and sort
* Clone existing fish as a starting point
* Live Minecraft-style tooltip preview as you type
* Manage lore schemes (view built-ins, create custom, apply to fish)
* No YAML knowledge required

### What It Looks Like

The web editor features:
* Modern gradient purple/blue theme
* Card-based fish display
* Full-screen modal for creating/editing
* Real-time validation
* Search/filter bar and sort controls

## Getting Started

### 1. Enable the Web Editor

Edit `plugins/SwagFishing/config.yml`:

```yaml
web-editor:
  enabled: true
  port: 8080
  bind-address: "0.0.0.0"  # Listen on all interfaces
  password: "changeme"      # CHANGE THIS!
```

> **Security Warning:** Always change the default password. The web editor has full control over your fish data.

### 2. Open Firewall (If Needed)

If running on a dedicated server, open port 8080:

**Linux (UFW):**
```bash
sudo ufw allow 8080/tcp
```

**Linux (iptables):**
```bash
sudo iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
```

**Windows Firewall:**
1. Control Panel → Windows Defender Firewall
2. Advanced Settings → Inbound Rules → New Rule
3. Port → TCP → Specific Port: 8080
4. Allow the connection

### 3. Access the Editor

1. **Reload plugin** or restart server
2. **Check console** for the URL:
   ```
   [SwagFishing] ========================================
   [SwagFishing] Web Editor Started!
   [SwagFishing] URL: http://192.168.1.100:8080
   [SwagFishing] Password: your_password_here
   [SwagFishing] Change password in config.yml!
   [SwagFishing] ========================================
   ```
3. **Open browser** and navigate to the URL
4. **Login** with your password

### 4. In-Game Command

Players with `swagfishing.admin` can get the URL in-game:

```
/fish web
```

## Fish Grid

The main view shows all fish in a card layout.

### Search and Filter

* **Search bar** - Filter by fish name, rarity, or biome
* **Sort controls** - Sort by name, rarity, XP reward, or sell price (ascending or descending)

### Card Information
Each card displays:
* Fish Name (colored)
* Rarity Badge (colored pill)
* Fish ID
* Material Type
* Rewards: XP, Essence, Value
* Edit / Delete / Clone buttons

### Card Colors
Rarity badges are color-coded:
* Quartz - White/Gray
* Emerald - Green
* Sapphire - Blue
* Ruby - Red
* Amethyst - Purple

### Clone Fish

Click the **Clone** button on any fish card to open the create form pre-filled with that fish's data. Useful for creating variations of existing fish. You must set a new unique Fish ID before saving.

## Creating a Fish

### Step 1: Click "Create New Fish"

The create modal opens with a comprehensive form.

### Step 2: Fill Basic Info

**Required Fields:**
* **Fish ID** - Unique identifier (lowercase, underscores only)
  * Example: `my_awesome_fish`
* **Display Name** - Name shown to players
  * Example: `&bMy Awesome Fish`
  * Supports color codes and hex colors (see below)
* **Rarity** - Choose from dropdown:
  * Quartz (Common)
  * Emerald (Uncommon)
  * Sapphire (Rare)
  * Ruby (Very Rare)
  * Amethyst (Mythical)
* **Material** - Minecraft item type (COD, SALMON, TROPICAL_FISH, PUFFERFISH, etc.)

**Optional Fields:**
* **Custom Model Data** - For resource packs (number)
* **Description** - Flavor text shown in lore

### Step 3: Set Location Requirements

**Biomes** (comma-separated):
```
OCEAN, DEEP_OCEAN, RIVER
```

**Time:**
* ANY, DAY, NIGHT, DAWN, DUSK

**Weather:**
* ANY, CLEAR, RAIN, THUNDER

**Y-Levels:**
* Min Y-Level and Max Y-Level (-64 to 320)

**Weight:**
* How often this fish spawns relative to others in the same conditions
* Higher = more common (e.g., 100 = very common, 5 = very rare)

### Step 4: Configure Rewards

| Field | Description |
|-------|-------------|
| XP Reward | Experience points; goes to FISHER job if FleaJobs is installed |
| Essence | Custom currency amount |
| Sell Price | Money value (requires Vault) |
| Gutting Essence | Essence gained from gutting this fish |
| Min/Max Size | Fish size range (cosmetic) |

### Step 5: Live Preview

As you type, the **Live Preview** panel on the right shows a real Minecraft-style tooltip of the fish item, updating in real-time. This reflects the display name (with color), rarity, description, stats, and any lore you add.

### Step 6: Add Lore (Optional)

Lore is **auto-generated** from the fish stats (via lore schemes), but you can override it with custom lines:

1. Type a lore line in the input
2. Click "Add Line"
3. Line appears with a remove (×) button
4. Repeat for multiple lines

If you leave lore empty, the fish's rarity default scheme is applied automatically.

### Step 7: Add Catch Commands (Optional)

Commands executed when the fish is caught. Placeholders:
* `{player}` - Player name
* `{fish}` - Fish name (no color codes)
* `{rarity}` - Rarity name

**Examples:**
```
broadcast &e{player} caught a rare fish!
give {player} diamond 1
```

### Step 8: Save

1. Click "Save Fish"
2. Fish appears in the grid
3. Run `/fish reload` in-game to activate

## Editing a Fish

1. Find the fish in the grid
2. Click "Edit"
3. Form pre-fills with current values
4. Make changes
5. Click "Save Fish"
6. Run `/fish reload` in-game

> You can only edit **custom fish** (from custom_fish.yml). Base fish from fish.yml cannot be edited through the web editor.

## Deleting a Fish

1. Find the fish in the grid
2. Click "Delete"
3. Confirm in the popup dialog
4. Run `/fish reload` in-game

## Schemes Tab

The Schemes tab lets you manage lore templates. See [Lore Schemes](schemes.md) for full documentation.

### What You Can Do

* View the 5 built-in schemes (one per rarity: default_quartz through default_amethyst)
* Clone a built-in scheme to create a custom version
* Create new custom schemes from scratch
* Edit or delete custom schemes
* Apply a scheme to fish by leaving fish lore empty (the rarity default scheme is auto-applied)

### Built-in Schemes (Read-Only)

Built-in schemes cannot be edited or deleted directly. Clone them first, then customize.

## Color Picker

In the display name and lore fields, a **Color Picker** button opens a color selector. Choosing a color inserts a hex color code at the current cursor position:

```
&#RRGGBB
```

**Supported color formats:**
* `&0` through `&f` — legacy Minecraft color codes
* `&#RRGGBB` — hex color (Adventure/Paper format)
* `<#RRGGBB>` — Adventure component format
* `&l`, `&o`, `&n`, `&m`, `&r` — formatting codes (bold, italic, underline, strikethrough, reset)

## Tips & Best Practices

### Naming Fish IDs

Good IDs:
* `golden_trout`
* `fire_bass`
* `mystic_eel`

Bad IDs:
* `Golden Trout` (spaces not allowed)
* `fire-bass` (hyphens not allowed)
* `Mystic_Eel` (use lowercase)

### Balancing Rewards

Use this as a guideline:

| Rarity | XP | Essence | Price |
|--------|----|---------|-------|
| Quartz | 5-10 | 2-3 | $10-20 |
| Emerald | 15-25 | 5-8 | $50-100 |
| Sapphire | 30-50 | 10-20 | $150-250 |
| Ruby | 75-150 | 30-50 | $400-750 |
| Amethyst | 200-500 | 100-200 | $1000-2000 |

### Setting Spawn Weights

* Common fish: 80-100
* Uncommon fish: 40-60
* Rare fish: 20-35
* Very Rare fish: 8-15
* Mythical fish: 1-5

Weight is relative to other fish available in the same biome/conditions.

## Troubleshooting

### Can't Access Web Editor

1. Is `enabled: true` in config?
2. Is the server running?
3. Is your firewall blocking port 8080?
4. Try `http://localhost:8080` if on the same machine
5. Check console for "Web Editor Started!"

### "Invalid Password" Error

1. Check `config.yml` for the current password
2. Run `/fish web` in-game to see the password
3. Password is case-sensitive with no extra spaces

### Fish Not Appearing In-Game

1. Click "Save Fish" in the web editor
2. Run `/fish reload` in-game
3. Check console for "Loaded X fish"
4. If still missing, check `custom_fish.yml` for YAML syntax errors

## Security Notes

* Change the default password immediately after install
* Use a strong password (12+ characters)
* Only share access with trusted admins
* Consider binding to `127.0.0.1` if only local access is needed:

```yaml
web-editor:
  bind-address: "127.0.0.1"
```

## API Endpoints

For developers wanting to integrate with the web editor programmatically:

```
POST   /api/auth              - Login (returns bearer token)
GET    /api/fish              - List all fish
GET    /api/fish/{id}         - Get specific fish
POST   /api/fish              - Create fish
PUT    /api/fish/{id}         - Update fish
DELETE /api/fish/{id}         - Delete fish
GET    /api/schemes           - List all schemes
POST   /api/schemes           - Create custom scheme
PUT    /api/schemes/{id}      - Update scheme (built-ins protected)
DELETE /api/schemes/{id}      - Delete scheme (built-ins protected)
```

All endpoints require `Authorization: Bearer {password}` header (the plaintext password as the token).

## Next Steps

* [Creating Custom Fish](creating-fish.md) — full YAML field reference
* [Lore Schemes](schemes.md) — template system for fish lore
