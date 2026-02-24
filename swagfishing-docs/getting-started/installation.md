# 📦 Installation

## Requirements

Before installing SwagFishing, ensure your server meets these requirements:

### Minimum Requirements
* **Minecraft:** 1.21+ (Paper or Spigot)
* **Java:** 21+
* **RAM:** 512MB minimum allocated to plugin
* **Permissions Plugin:** Any (LuckPerms recommended)

### Recommended Dependencies
* **Vault** - For economy integration (optional)
* **FleaJobs** - For job system integration (optional)
* **PlaceholderAPI** - For placeholder support (optional)
* **WorldGuard** - For region protection (optional)
* **ModelEngine** - For boss fish models (optional, future feature)

## Quick Installation

### Step 1: Download Plugin

1. Download the latest `SwagFishing.jar` from releases
2. Verify the file is for your Minecraft version

### Step 2: Install Plugin

1. **Stop your server** (required)
2. Place `SwagFishing.jar` in your `plugins/` folder
3. **Start your server**

The plugin will automatically:
* Generate default configuration files
* Create the database
* Load base fish

### Step 3: Verify Installation

Run this command in console or as an admin:

```
swagfish version
```

You should see:
```
SwagFishing v1.0.0
Minecraft: 1.21+
Loaded Fish: 14
```

## First-Time Setup

### 1. Configure Web Editor (Optional)

The web editor allows you to create custom fish through a beautiful web interface.

Edit `plugins/SwagFishing/config.yml`:

```yaml
web-editor:
  enabled: true
  port: 8081
  bind-address: "0.0.0.0"
  password: "changeme"  # CHANGE THIS!
```

**Important:** Change the password immediately!

Access the web editor at: `http://YOUR_SERVER_IP:8081`

### 2. Set Up Economy (Optional)

If using Vault for economy:

1. Install Vault plugin
2. Install an economy plugin (EssentialsX, CMI, etc.)
3. Restart server
4. SwagFishing will auto-detect Vault

Check console for:
```
[SwagFishing] Vault detected and hooked successfully!
```

### 3. Configure FleaJobs (Optional)

If using FleaJobs for job integration:

1. Install FleaJobs plugin
2. Restart server
3. SwagFishing will use FleaJobs for leveling

Check console for:
```
[SwagFishing] FleaJobs detected! Using FleaJobs leveling system.
```

### 4. Test Fishing

1. Join your server
2. Get a fishing rod
3. Go to an ocean biome
4. Start fishing!
5. Run `/swagfish codex` to view your catches

## File Structure

After installation, you'll have:

```
plugins/SwagFishing/
├── config.yml           # Main configuration
├── fish.yml             # Base fish definitions
├── custom_fish.yml      # Your custom fish
├── swagfishing.db       # SQLite database
└── web/                 # Web editor files
    └── index.html
```

## Updating

### From Earlier Version

1. **Stop server**
2. **Backup your data:**
   ```
   plugins/SwagFishing/swagfishing.db
   plugins/SwagFishing/custom_fish.yml
   ```
3. Replace `SwagFishing.jar`
4. **Start server**
5. Check console for migration messages

{% hint style="warning" %}
**Always backup your database before updating!**
{% endhint %}

## Troubleshooting Installation

### Plugin Won't Load

**Issue:** Server won't start or plugin is red in `/plugins`

**Solutions:**
1. Check Java version: `java -version` (must be 21+)
2. Check server type: Must be Paper or Spigot
3. Check console for errors
4. Remove other fishing plugins

### Database Errors

**Issue:** `SQLException` errors in console

**Solutions:**
1. Delete `swagfishing.db` (fresh install only)
2. Check file permissions
3. Ensure SQLite support (built into plugin)

### Web Editor Won't Start

**Issue:** Can't access web editor at `http://IP:8081`

**Solutions:**
1. Check `config.yml` - is `enabled: true`?
2. Check if port 8081 is open in firewall
3. Try different port in config
4. Check console for "Web Editor Started!"

### Fish Not Loading

**Issue:** `/swagfish reload` shows "Loaded 0 fish"

**Solutions:**
1. Check `fish.yml` exists in `plugins/SwagFishing/`
2. Check YAML syntax (no tabs, proper indentation)
3. Delete `fish.yml` - plugin will regenerate
4. Check console for YAML errors

## Next Steps

{% content-ref url="configuration.md" %}
[configuration.md](configuration.md)
{% endcontent-ref %}

{% content-ref url="quick-start.md" %}
[quick-start.md](quick-start.md)
{% endcontent-ref %}

{% content-ref url="../core-features/fishing-system.md" %}
[fishing-system.md](../core-features/fishing-system.md)
{% endcontent-ref %}
