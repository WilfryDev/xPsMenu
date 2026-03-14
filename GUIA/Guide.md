<div align="center">

# 🎢 xPsMenu - Official User Guide

![foto3](https://cdn.modrinth.com/data/cached_images/64923da0dc8b1c5f8bf373e9c944603a7bf679f7.png)
![foto2](https://cdn.modrinth.com/data/cached_images/95ef835f06d7e9ad0fc4db5dfd634d11a1acb2fb.png)
![foto1](https://cdn.modrinth.com/data/cached_images/78a5b931bf4831e47375df772082aa07617f8ba9.png)

Do you want to acquire the best ES/EN configuration?
- ¡Enter the discord!
  - It helps us a lot.

</div>

---

## 📌 Requirements

* **Minecraft Version:** 1.19.4 or higher.
* **ProtectionStones:** v2.10+ (Highly recommended to use the version provided in our download folder).
* **WorldGuard & WorldEdit:** Required for region management.
* **PlaceholderAPI:** Optional, but highly recommended.

---

## 📥 Installation & Setup

1. Stop your server.
2. Download the `xPsMenu-v1.0.0.jar` and place it in your `/plugins/` folder.
3. **Crucial Step:** You must use the `messages.yml` file for ProtectionStones provided in the download folder. Replace your existing ProtectionStones `messages.yml` with this one to ensure the menus function properly.
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

### Add to your `build.gradle`:
```gradle
dependencies {
    compileOnly fileTree(dir: 'libs', include: 'xPsMenu-v1.0.0.jar')
}
Example Usage:
Java
import jn.willfrydev.xPsMenuAPI;
import org.bukkit.entity.Player;

public class MyCustomPlugin {
    
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