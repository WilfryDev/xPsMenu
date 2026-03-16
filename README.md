<div align="center">
  <h1>🛡️ xPsMenu - Premium ProtectionStones GUI</h1>
  <p>The most advanced, interactive, and fully customizable GUI menu for ProtectionStones.</p>
  
  [![Version](https://img.shields.io/badge/Version-v1.0.0-blue.svg)]()
  [![bStats](https://img.shields.io/badge/bStats-30106-green.svg)]()
  [![PlaceholderAPI](https://img.shields.io/badge/PlaceholderAPI-Supported-yellow.svg)]()
</div>

---

## ✨ Features
**xPsMenu** takes the classic ProtectionStones experience and transforms it into a modern, visual, and premium system for your players. 

* 🎨 **100% Customizable:** Every single menu, item, lore, and message is fully editable (`gui.yml`, `flags.yml`, `selector.yml`, `config.yml`).
* 🌈 **Hex Colors & MiniMessage:** Full support for modern Hex color codes (`&#FFFFFF`) to make your menus pop out.
* 📋 **Dynamic Region Selector:** A live, auto-updating GUI showing all player regions with an interactive filter (View ALL, OWNERS, or MEMBERS).
* 👤 **Advanced Player Management:** View members and owners using real Player Heads! Kick players directly via Shift + Right-Click.
* ✨ **0-Lag Particle System:** When a protection block is hidden, only the owner will see beautiful magical particles indicating its location (highly optimized, 0 server lag).
* 🚀 **OP / VIP Bypass:** Instantly teleport to your region without the 3-second cooldown using a permission node.
* 🛠️ **Admin Tools:** Nuke all regions from the server database with a single safety-confirmed command.
* 🔌 **Developer API:** Easily hook into the plugin to open menus from other custom plugins or NPCs.

---

## 📥 Installation
1. Stop your server.
2. Download the `xPsMenu-v1.0.0.jar` and place it in your `/plugins/` folder.
3. Ensure you have the required dependencies:
   * **ProtectionStones** (2.10+)
   * **WorldGuard** & **WorldEdit**
   * **PlaceholderAPI** (Optional, but highly recommended)
4. Start the server.
5. Customize the configuration files inside `/plugins/xPsMenu/` and type `/psmenu reload`.

---

## ⌨️ Commands & Permissions

### Player Commands
* `Shift + Right Click` (on a protection block) - Opens the main management GUI for that specific region.
* `/psmenu` - Opens the dynamic Region Selector (Shows all your active regions).
* `/psmenu help` - Shows the help menu.

### Admin Commands
* `/psmenu reload` - Reloads all configuration files seamlessly.
  * **Permission:** `psmenu.admin`
* `/psmenu clearall confirm` - ⚠️ *DANGER!* Wipes every single ProtectionStones region from the server database.
  * **Permission:** `psmenu.admin`

### Extra Permissions
* `psmenu.bypass` - Bypasses the 3-second teleportation delay. Instant teleport!

---

## 📊 Placeholders

### Internal Menu Variables
Use these exclusively inside your `gui.yml` and `flags.yml` to display dynamic data:
* `%region%` - Displays the ID of the region currently being edited.
* `%hidden_status%` - Displays the current state of the block (e.g., Hidden ✘ or Visible ✔ - editable in config).
* *Note: You can also use any global PlaceholderAPI variable inside the menus (like `%player_name%`).*

### PlaceholderAPI Variables (Global)
You can use these variables anywhere on your server (Scoreboards, Holograms, Chat, etc.):
* `%xpsmenu_version%` - Displays the current plugin version.
* `%xpsmenu_player%` - Displays the player's name.

---

## 💻 Developer API
Building a custom core or an NPC script? You can easily hook into **xPsMenu** to open interfaces for your players using our static API.

### Add to your build.gradle:
* We will soon update the API for greater control
```gradle

dependencies {
    compileOnly fileTree(dir: 'libs', include: 'xPsMenu-v1.0.0.jar')
}
Example Usage:
Java
import jn.willfrydev.xPsMenuAPI;
import org.bukkit.entity.Player;

public class xTestPlugin {
    
    public void openMenuForPlayer(Player player, String regionId) {

        // Opens the main Editor GUI for a specific region

        xPsMenuAPI.openMainMenu(player, "ps10x64y5z");
    }

    public void openListForPlayer(Player player) {

        // Opens the Dynamic Region Selector GUI for the player

        xPsMenuAPI.openSelector(player);
    }
}
```

<div align="center">
<b>Developed with ❤️ by <a href="https://xplugins.es">xPlugins</a></b>
</div>