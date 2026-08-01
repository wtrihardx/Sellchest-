# 🪙 Prime SellChest – Ultimate Automated Selling System

> [!WARNING]
> ### ⚠️ IMPORTANT REQUIREMENTS
> 
> Please make sure you have installed these **3 required plugins**: 
> * 💳 **Vault**
> * 🏷️ **EconomyShopGUI**
> * 🔮 **Any Hologram plugin** *(e.g. DecentHolograms)*
> 
> Ensure all of them are placed into your `/plugins` folder!  
> 🚨 **Without these 3 plugins, SellChest will either not function properly or won't start at all.**

**SellChest** is an advanced, lightweight, and highly optimized Paper 1.21 plugin engineered to automate item collection and selling on SkyBlock, Survival, and Factions servers. 

Instead of forcing players to spend endless hours manually sorting chests and traveling to shops, SellChest continuously vacuums nearby dropped items, calculates payouts instantly via **EconomyShopGUI**, splits revenues among co-op team members, and displays real-time statistics using interactive 3D holograms.

---

## 🌟 Key Features

### 🧹 Automated Item Vacuuming
* **Area Coverage:** Automatically scans an **8×8 area (4 blocks high)** around the chest every second.
* **Smart Pickup:** Pulls dropped items directly into the chest's internal storage without causing entity lag.

### 💸 Dynamic Economy & Price Integration
* **EconomyShopGUI Hook:** Prices are dynamically read directly from your existing `EconomyShopGUI` shop setups—no need to manually configure item prices twice!
* **Chest Tiers:** Supports multi-tier economy rates out of the box:
  * 📦 **Normal Chest:** Sells items at **1× standard price**.
  * ⭐ **Premium Chest:** Sells items at **2× multiplier rate**.
* **Safeguard System:** Unpriced items or items not listed in `EconomyShopGUI` safely remain inside the chest (zero risk of accidental loss or item voiding).

### 👥 Multi-Member Co-op & Revenue Splitting
* **Team Selling:** Share profits automatically with up to **3 co-op members** per chest.
* **Custom Share Percentages:** Set exact profit splits (e.g., 50% Owner, 25% Member A, 25% Member B) ensuring the total payout equals 100%.
* **Vault Integration:** Money is deposited directly into all players' balances in real time via Vault.

### 🔮 Dynamic Live Holograms
* **Real-time Stats:** Each placed SellChest projects a customizable hologram displaying:
  * Chest Owner Name
  * Chest Tier (*Normal / Premium*)
  * Total Lifetime Earnings
  * Active Sales Boost Multiplier Indicator
* Updates dynamically on every selling interval.

### ⚡ Global Server Sales Boosts
* Trigger server-wide economy events using `/sellchest boost <minutes>`.
* **Doubles all chest earnings** (2× multiplier) across the entire server for the specified duration.
* Great for weekend events, voting rewards, or donor perks!

### 🛠️ Comprehensive Admin GUI Panel
Take full control of your server's economy through a clean, intuitive Admin Interface (`/sellchest adminpanel`):
* Inspect every chest placed on the server.
* Transfer chest ownership between players.
* Modify co-op share configurations and permissions.
* Reset total earnings statistics.
* Edit hologram displays or purge unwanted chests instantly.

---

## ⚙️ How It Works (Step-by-Step Pipeline)

1. **Item Collection (Suction Phase):** Every 1 second (20 ticks), the plugin checks the $8 \times 8 \times 4$ bounding box around every registered SellChest. Any entity matching dropped items is instantly ingested into the chest's inventory.
2. **Price Verification & Selling Phase:** The chest inventory is scanned against **EconomyShopGUI** price index. 
   * If an item has a valid price $\rightarrow$ It is sold at the chest's tier multiplier (*1× for Normal*, *2× for Premium*).
   * If a **Global Boost** is active $\rightarrow$ Payout is multiplied by an extra $2\times$.
   * If an item is NOT in the shop $\rightarrow$ It remains safely stored in the chest inventory.
3. **Profit Distribution Phase:** Total earnings are calculated and divided strictly according to configured co-op shares (totaling 100%). Money is deposited straight into player accounts via **Vault**.
4. **Hologram Sync Phase:** Live holograms update instantly to reflect newly accumulated total earnings and current boost states.

---

## 📦 Requirements & Hard Dependencies

> ⚠️ **IMPORTANT HARD DEPENDENCY NOTICE:**  
> SellChest **REQUIRES** the following dependencies to be installed in your server's `/plugins` folder. Without these plugins, SellChest **WILL NOT FUNCTION OR START UP**.

| Dependency | Purpose | Required Version |
| :--- | :--- | :--- |
| ☕ Java 1.19.4+ | Execution Environment | Java 1.19.4+ |
| 📄 Paper 1.19.4+ | Server Core Software | Paper 1.19.4+ |
| 💳 **Vault** | Economy & Account Management | Latest |
| 🏷️ **EconomyShopGUI** | Source for Item Pricing | Latest |
| 🔮 **Hologram Plugin** | Displays live chest holograms *(e.g., DecentHolograms, HolographicDisplays, etc.)* | Any compatible hologram plugin |

---

## 💻 Commands & Permissions

All commands are controlled via standard permission nodes. Give `sellchest.admin` to server administrators and `sellchest.use` to general players.

| Command | Permission | Description |
| :--- | :--- | :--- |
| `/sellchest` | `sellchest.use` | Displays command usage and available options. |
| `/sellchest reload` | `sellchest.admin` | Reloads all configuration files and active boost states. |
| `/sellchest give <player> <normal\|premium>` | `sellchest.admin` | Gives a specific Sell Chest item to a player's inventory. |
| `/sellchest remove <player> <reason>` | `sellchest.admin` | Removes all chests owned by a player (both placed & inventory) and notifies them. |
| `/sellchest reset <player>` | `sellchest.admin` | Resets total earnings statistics to zero for all chests owned by the player. |
| `/sellchest boost <minutes>` | `sellchest.admin` | Activates a server-wide global sell boost for the specified duration. |
| `/sellchest adminpanel` | `sellchest.admin` | Opens the main Admin Management Panel GUI. |

---

## ❓ Frequently Asked Questions (FAQ)

**Q: What happens if an item inside the chest isn't listed in EconomyShopGUI?**  
*A: Nothing! The plugin strictly leaves unpriced items inside the chest inventory. No fallback prices are used, protecting your server economy from unintended item sales.*

**Q: Can players add more than 3 co-op members?**  
*A: No, SellChest is strictly capped at a maximum of 3 co-op members per chest to maintain balanced economy scaling and clean UI menus.*

**Q: What happens if a player goes offline?**  
*A: Their chests continue to function normally as long as the chunk is loaded. Earnings are automatically deposited directly to their balance via Vault even while offline!*

---

## 🤝 Support & Discord Community

Found a bug? Need help configuring the plugin? Have a feature suggestion?  
We are always happy to help!

  # 💬 **[Join our Discord Server](https://discord.gg/x9yQKVqT9C)** to open a support ticket, get developer assistance, or report issues!

[PreimeSellchest1.0.1](https://modrinth.com/project/mZLelxwf) From Mordinth
 
 [PreimeSellchest1.0.1](https://github.com/wtrihardx/prime-_sellchest/releases/download/Sellchest/SellChest-1.0.2.jar) From Github


  ## ON EVERY SITE THE PLUGIN WILL BE UPDATED **
 
 

