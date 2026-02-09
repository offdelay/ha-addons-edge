# Offdelay HA Add-ons Edge

This repository (`ha-addons-edge`) serves as the origin/source repository for Offdelay's Home Assistant add-ons. It feeds into two separate repositories that can be added to the Home Assistant add-on store: the stable `ha-addons` repository and the edge repository.

## Which Repository Should You Use?

There are two versions of this repository:

### **ha-addons** (Stable) - Recommended for Most Users
- **Stable, tested releases** - Add-ons are periodically pushed from the edge version after testing
- **Recommended for production use** - More reliable and stable
- **Suitable for most users** - Best choice unless you need the absolute latest features

### **ha-addons-edge** (Latest) - For Early Adopters
- **Latest features instantly** - Updates are pushed immediately without a trail period
- **May contain bugs** - Not recommended for production environments
- **Use only if you need cutting-edge features** - For users who want to test/use the newest functionality right away

## Installation

### Installing the Stable Repository (Recommended)

For most users, we recommend installing the stable version:

1. [Click this link to add the stable repository to the Add-on Store](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https://github.com/offdelay/ha-addons) and click Add.
   - If that link doesn't work, then
        1. Go to http://homeassistant.local:8123/hassio/store (or whatever your Home Assistant URL is)
        2. Click the 3 dots icon in the upper right, then click `Repository`
        3. In the Add field, paste `https://github.com/offdelay/ha-addons` 
        4. Click `+ Add` then `Close`
2. Scroll to the section "Offdelay HA Add-ons"
3. Select an add-on and click Install
4. Start the add-on and configure as needed

### Installing the Edge Repository (Advanced Users Only)

⚠️ **Warning**: Use only if you need the latest features immediately or want to help with troubleshooting potential issues.

1. [Click this link to add this edge repository to the Add-on Store](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https://github.com/offdelay/ha-addons-edge) and click Add.
   - If that link doesn't work, then
        1. Go to http://homeassistant.local:8123/hassio/store (or whatever your Home Assistant URL is)
        2. Click the 3 dots icon in the upper right, then click `Repository`
        3. In the Add field, paste `https://github.com/offdelay/ha-addons-edge` 
        4. Click `+ Add` then `Close`
2. Scroll to the section "Offdelay HA Add-ons (Edge)"
3. Select an add-on and click Install
4. Start the add-on and configure as needed

**Note**: You can install both repositories, but be aware that add-ons will appear with the same name in Home Assistant.

Here is the raw Markdown code. You can copy the block below and paste it directly into your README.md file.

Markdown
# Offdelay HA Add-ons Edge

This repository (`ha-addons-edge`) serves as the origin/source repository for Offdelay's Home Assistant add-ons. It feeds into two separate repositories that can be added to the Home Assistant add-on store: the stable `ha-addons` repository and the edge repository.

## Which Repository Should You Use?

There are two versions of this repository:

### **ha-addons** (Stable) - Recommended for Most Users
- **Stable, tested releases** - Add-ons are periodically pushed from the edge version after testing
- **Recommended for production use** - More reliable and stable
- **Suitable for most users** - Best choice unless you need the absolute latest features

### **ha-addons-edge** (Latest) - For Early Adopters
- **Latest features instantly** - Updates are pushed immediately without a trail period
- **May contain bugs** - Not recommended for production environments
- **Use only if you need cutting-edge features** - For users who want to test/use the newest functionality right away

---

## 🛠 Developer Guide: Updating the Repositories

To keep the ecosystem up to date, follow these steps to sync the Edge and Stable repositories.

### Step 1: Update the Edge Repository
The Edge repository is updated by pulling the latest code from individual addon sources.

1. **Pull Latest Addons:** Navigate to each specific addon folder locally.
   * Example: `cd Cloudflared-addon`
   * Run: `git pull`
2. **Sync Content:** Copy the contents of the internal addon folder (e.g., the `cloudflared` folder inside the addons source) and paste it into the corresponding folder in `HA-addons-edge/`.
   * Example: Copy contents of `addons/cloudflared/*` → `HA-addons-edge/Cloudflared/`
3. **Repeat:** Do this for every addon in the collection.
4. **Commit & Push:** Commit these changes to the `ha-addons-edge` GitHub repository.

### Step 2: Update the Stable Repository
To ensure stability, updates are staged in a time-stamped branch before reaching production.

1. **Stage to a Release Branch:** Push the current state of `ha-addons-edge` to the **stable** remote using a branch named by the current year and month.
   * Format: `stable-YYYY-MM` (e.g., `stable-2026-02`)
   * run: `git checkout -b stable-2026-02` (when still on origin - main)
   * run: `git push stable stable-2026-02`
2. **Cooling Period:** Leave the code in this branch for a few weeks to allow for testing and bug discovery.
3. **Create Pull Request:** After the testing period, create a Pull Request from the `stable-YYYY-MM` branch into the `main` branch of the `ha-addons` (stable) repository.
4. **Merge:** Once approved, merge the PR to update the stable repository for all users.