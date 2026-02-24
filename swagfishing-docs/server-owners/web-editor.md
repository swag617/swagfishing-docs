# 🌐 Web Editor

The SwagFishing Web Editor is a beautiful, user-friendly interface that lets server admins create and manage custom fish without touching YAML files.

## Overview

### What Can You Do?

* ✅ **Create new fish** with a visual form
* ✅ **Edit existing custom fish**
* ✅ **Delete custom fish**
* ✅ **View all fish** in a card grid
* ✅ **Live preview** of fish statistics
* ✅ **No YAML knowledge** required!

### What It Looks Like

The web editor features:
* Modern gradient purple/blue theme
* Card-based fish display
* Full-screen modal for creating/editing
* Real-time validation
* Beautiful animations and transitions

## Getting Started

### 1. Enable the Web Editor

Edit `plugins/SwagFishing/config.yml`:

```yaml
web-editor:
  enabled: true
  port: 8081
  bind-address: "0.0.0.0"  # Listen on all interfaces
  password: "changeme"      # CHANGE THIS!
```

{% hint style="danger" %}
**Security Warning:** Always change the default password! The web editor has full control over your fish.
{% endhint %}

### 2. Open Firewall (If Needed)

If running on a dedicated server, open port 8081:

**Linux (UFW):**
```bash
sudo ufw allow 8081/tcp
```

**Linux (iptables):**
```bash
sudo iptables -A INPUT -p tcp --dport 8081 -j ACCEPT
```

**Windows Firewall:**
1. Control Panel → Windows Defender Firewall
2. Advanced Settings → Inbound Rules → New Rule
3. Port → TCP → Specific Port: 8081
4. Allow the connection

### 3. Access the Editor

1. **Reload plugin** or restart server
2. **Check console** for the URL:
   ```
   [SwagFishing] ========================================
   [SwagFishing] Web Editor Started!
   [SwagFishing] URL: http://192.168.1.100:8081
   [SwagFishing] Password: your_password_here
   [SwagFishing] Change password in config.yml!
   [SwagFishing] ========================================
   ```
3. **Open browser** and navigate to the URL
4. **Login** with your password

### 4. In-Game Command

Players with `swagfishing.admin` can get the URL:

```
/swagfish web
```

This shows:
* Web editor status (Running/Stopped)
* Clickable URL (hover to see "Click to open")
* Current password

## Creating a Fish

### Step 1: Click "Create New Fish"

The create modal opens with a comprehensive form.

### Step 2: Fill Basic Info

**Required Fields:**
* **Fish ID** - Unique identifier (lowercase, underscores)
  * Example: `my_awesome_fish`
  * Auto-formatted (removes spaces, special chars)
* **Display Name** - Name shown to players
  * Example: `&bMy Awesome Fish`
  * Supports color codes (`&a` = green, `&c` = red)
* **Rarity** - Choose from dropdown:
  * Quartz (Common)
  * Emerald (Uncommon)
  * Sapphire (Rare)
  * Ruby (Very Rare)
  * Amethyst (Mythical)
* **Material** - Minecraft item type:
  * COD
  * SALMON
  * TROPICAL_FISH
  * PUFFERFISH

**Optional Fields:**
* **Custom Model Data** - For resource packs (number)
* **Description** - Flavor text shown in lore

### Step 3: Set Location Requirements

**Biomes** (comma-separated):
```
OCEAN, DEEP_OCEAN, RIVER
```

**Time:**
* ANY - Available all times
* DAY - Daytime only
* NIGHT - Nighttime only
* DAWN - Sunrise
* DUSK - Sunset

**Weather:**
* ANY - Any weather
* CLEAR - Clear skies only
* RAIN - Raining only
* THUNDER - Thunderstorm only

**Y-Levels:**
* Min Y-Level: -64 to 320
* Max Y-Level: -64 to 320

**Weight:**
* How often this fish spawns relative to others
* Higher = more common
* Example: 100 = very common, 5 = very rare

### Step 4: Configure Rewards

**XP Reward:**
* Experience points awarded
* Goes to FleaJobs FISHER job (if installed)
* Example: 50 XP

**Essence:**
* Custom currency amount
* Used for totems, upgrades
* Example: 15 essence

**Sell Price:**
* Money value (requires Vault)
* Example: 150.00

**Gutting Essence:**
* Essence gained from gutting (future feature)
* Example: 25

**Size Range:**
* Min Size: 0.1+
* Max Size: 0.1+
* Currently cosmetic

### Step 5: Add Lore (Optional)

Lore is **auto-generated** based on fish stats, but you can add custom lines:

1. Type a lore line in the input
2. Click "Add Line"
3. Line appears below with remove (×) button
4. Repeat for multiple lines

**Example:**
```
&7This is a magical fish
&7Found only in mystical waters
```

### Step 6: Add Catch Commands (Optional)

Commands execute when fish is caught. Supports:

**Broadcast:**
```
broadcast &e{player} caught a rare fish!
```

**Play Sound:**
```
playsound ENTITY_LIGHTNING_BOLT_THUNDER 1.0 1.0
```

**Console Command:**
```
give {player} diamond 1
```

**Placeholders:**
* `{player}` - Player name
* `{fish}` - Fish name (no color)
* `{rarity}` - Rarity name

### Step 7: Save

1. Click "Save Fish"
2. Wait for success message
3. Fish appears in the grid!
4. Run `/swagfish reload` in-game

## Editing a Fish

1. **Find the fish** in the grid
2. **Click "Edit"** button
3. **Form pre-fills** with current values
4. **Make changes**
5. **Click "Save Fish"**
6. **Reload in-game:** `/swagfish reload`

{% hint style="info" %}
You can only edit **custom fish** (from custom_fish.yml). Base fish (from fish.yml) cannot be edited through the web editor.
{% endhint %}

## Deleting a Fish

1. **Find the fish** in the grid
2. **Click "Delete"** button
3. **Confirm** in popup dialog
4. **Fish removed** from custom_fish.yml
5. **Reload in-game:** `/swagfish reload`

## Fish Grid

The main view shows all fish in a beautiful card layout:

### Card Information
Each card displays:
* **Fish Name** (colored)
* **Rarity Badge** (colored pill)
* **Fish ID**
* **Material Type**
* **Rewards:** XP, Essence, Value
* **Edit/Delete Buttons**

### Card Colors
Rarity badges are color-coded:
* ⚪ **Quartz** - White/Gray
* 💚 **Emerald** - Green
* 💙 **Sapphire** - Blue
* ❤️ **Ruby** - Red
* 💜 **Amethyst** - Purple

## Tips & Best Practices

### Naming Fish IDs

✅ **Good IDs:**
* `golden_trout`
* `fire_bass`
* `mystic_eel`

❌ **Bad IDs:**
* `Golden Trout` (spaces)
* `fire-bass` (hyphens)
* `Mystic_Eel` (capitals)

### Using Color Codes

**Format:** `&[code][text]`

**Common Colors:**
* `&a` - Green
* `&b` - Aqua
* `&c` - Red
* `&d` - Pink
* `&e` - Yellow
* `&f` - White

**Formatting:**
* `&l` - **Bold**
* `&o` - *Italic*
* `&n` - Underline

**Example:**
```
&b&lMystic &f&lCod
```
Result: **Mystic Cod** (aqua bold, white bold)

### Balancing Rewards

Use this as a guideline:

| Rarity | XP | Essence | Price |
|--------|-----|---------|-------|
| Quartz | 5-10 | 2-3 | $10-20 |
| Emerald | 15-25 | 5-8 | $50-100 |
| Sapphire | 30-50 | 10-20 | $150-250 |
| Ruby | 75-150 | 30-50 | $400-750 |
| Amethyst | 200-500 | 100-200 | $1000-2000 |

### Setting Spawn Weights

**General Rules:**
* Common fish: 80-100
* Uncommon fish: 40-60
* Rare fish: 20-35
* Very Rare fish: 8-15
* Mythical fish: 1-5

**Remember:** Weight is relative to OTHER fish in the same biome/conditions!

## Troubleshooting

### Can't Access Web Editor

**Check these:**
1. Is `enabled: true` in config?
2. Is server running?
3. Is firewall blocking port 8081?
4. Try `http://localhost:8081` if on same machine
5. Check console for "Web Editor Started!"

### "Invalid Password" Error

1. Check `config.yml` for current password
2. Run `/swagfish web` to see password
3. Password is case-sensitive
4. Make sure no extra spaces

### Fish Not Appearing In-Game

After creating/editing fish:
1. Click "Save Fish" in web editor
2. **Must run** `/swagfish reload` in-game
3. Check console for "Loaded X fish"
4. If still not appearing, check YAML syntax in `custom_fish.yml`

### Changes Not Saving

1. Check browser console (F12) for errors
2. Ensure you have admin permission
3. Check server console for save errors
4. Verify `custom_fish.yml` file permissions

## Security Notes

{% hint style="warning" %}
**Important Security Practices:**
* Change default password immediately
* Use a strong password (12+ characters)
* Don't share password publicly
* Only give access to trusted admins
* Consider binding to `127.0.0.1` if only local access needed
{% endhint %}

### Binding to Localhost Only

If you only need local access (same machine as server):

```yaml
web-editor:
  bind-address: "127.0.0.1"  # Only localhost can access
```

Then use SSH tunnel or access locally.

## API Endpoints

For developers wanting to integrate:

```
POST   /api/auth          - Login (get token)
GET    /api/fish          - List all fish
GET    /api/fish/{id}     - Get specific fish
POST   /api/fish          - Create fish
PUT    /api/fish/{id}     - Update fish
DELETE /api/fish/{id}     - Delete fish
```

All endpoints require `Authorization: Bearer {password}` header.

## Next Steps

{% content-ref url="creating-fish.md" %}
[creating-fish.md](creating-fish.md)
{% endcontent-ref %}

{% content-ref url="../config-files/custom-fish.md" %}
[custom-fish.md](../config-files/custom-fish.md)
{% endcontent-ref %}
