# Offdelay HA Add-ons Edge

This repository (`ha-addons-edge`) serves as the origin/source repository for Offdelay's Home Assistant add-ons. It feeds into two separate repositories that can be added to the Home Assistant add-on store: the stable `ha-addons` repository and the edge repository.

## Which Repository Should You Use?

There are two versions of this repository:

### **ha-addons** (Stable) - Recommended for Most Users
- **Stable, tested releases** - Add-ons are periodically pushed from the edge version after testing
- **Recommended for production use** - More reliable and stable
- **Suitable for most users** - Best choice unless you need the absolute latest features

### **ha-addons-edge** (This Repository) - For Early Adopters
- **Latest features instantly** - Updates are pushed immediately without extensive testing
- **May contain bugs** - Not recommended for production environments
- **Use only if you need cutting-edge features** - For users who want to test the newest functionality right away

**💡 Recommendation: Start with the stable `ha-addons` repository. Only use `ha-addons-edge` if you specifically need the latest features and are comfortable with potential instability.**

## Installation

### Installing the Stable Repository (Recommended)

For most users, we recommend installing the stable version:

1. [Click this link to add the stable repository to the Add-on Store](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https://github.com/offdelay/ha-addons) and click Add.
   - If that link doesn't work, then
        1. Go to http://homeassistant.local:8123/hassio/store (or whatever your Home Assistant URL is)
        2. Click the 3 dots icon in the upper right, then click `Repository`
        3. In the Add field, paste `https://github.com/offdelay/ha-addons` 
        4. Click `+ Add` then `Close`
2. Scroll to the section "offdelay HA Add-ons"
3. Select an add-on and click Install
4. Start the add-on and configure as needed

### Installing the Edge Repository (Advanced Users Only)

⚠️ **Warning**: The edge repository contains untested, bleeding-edge updates. Use only if you need the latest features immediately and are comfortable troubleshooting potential issues.

1. [Click this link to add this edge repository to the Add-on Store](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https://github.com/offdelay/ha-addons-edge) and click Add.
   - If that link doesn't work, then
        1. Go to http://homeassistant.local:8123/hassio/store (or whatever your Home Assistant URL is)
        2. Click the 3 dots icon in the upper right, then click `Repository`
        3. In the Add field, paste `https://github.com/offdelay/ha-addons-edge` 
        4. Click `+ Add` then `Close`
2. Scroll to the section "offdelay HA Add-ons (Edge)"
3. Select an add-on and click Install
4. Start the add-on and configure as needed

**Note**: You can install both repositories, but be aware that add-ons will appear with the same name in home assistant.