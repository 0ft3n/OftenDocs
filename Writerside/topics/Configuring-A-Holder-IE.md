# Configuring A Holder

To create your very own custom holder, head to your `plugins/ItemEffects/holders/` folder, where you can create a new file,
name it `a-z,0-9,-_` lowercase and put the actual holder options inside it.

You can use the `plugins/ItemEffects/holders/_example.yml` holder for reference when creating a new holder.

Let's dive into the example config to see what it consists of:

## Example config

```yaml
# The ID of the holder is the name of the .yml file,
# for example power.yml has the ID of power
# You can place holders anywhere in this folder,
# including in subfolders if you want to organize your holder configs
# _example.yml is not loaded.

name: "&cReinforcement" # The name of the holder in-game

default-lore: # A lore appearing on the item with this holder applied
  - ""
  - "&c* &7&oWhile above &c&o50%&7&o health,"
  - "&c* &7&odeal &6&o3 &7&oadditional damage per hit"

conflicts: [] # A list of conflicting holder IDs
requirements: [] # A list of holders required to be on the item before applying this one

effects: # A list of effects that this holder will add to the item
  # (https://plugins.auxilor.io/effects/configuring-an-effect)
  - id: add_damage
    args:
      damage: 3
    triggers:
      - melee_attack

conditions: # A list of conditions for the effects to work (https://plugins.auxilor.io/effects/configuring-a-condition)
  - id: above_health_percent
    args:
      percent: 50

scrolls: # A list of scrolls (drag'n'drop solutions) to apply this holder without a command
  - id: "reinforcement_swords" # The ID of a scroll
    uses-slot: true # If this scroll should fill a slot in the item when applied (see limit configs in /plugins/ItemEffects/config.yml)
    updatable-lore: false # If set to true, holder lore will always be taken from `default-lore` so will change if you change it in config as well
    targets: # The items that the holder can be applied to, see targets.yml
      - sword
    item: player_head texture:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNzc3ZTQwYmIwYjM3MWIzNzQ1ZGZlNWVkNTIwMzNmZmNmYzhjODJmZWVmYzI1YjM0YmFjN2FlZDFmZjljZTU4ZiJ9fX0= # The scroll item
    usages: 3 # How many usages will one scroll item have
    name: "&fScroll: &cReinforcement &8(&bSwords&8)" # The scroll item name
    lore: # The scroll item lore
      - ""
      - "&fDrag'n'drop &fthis item onto your &bsword"
      - "&fto apply &cReinforcement &fto it &8(&fwhile in &6main hand&8):"
      - "&c* &7&oWhile above &c&o50%&7&o health,"
      - "&c* &7&odeal &6&o3 &7&oadditional damage per hit"
      - ""
      - "&fUsages left: &a%usages%"
      - ""
    apply-effects: # A list of effects that will trigger once when player applies scroll to an item
      # (https://plugins.auxilor.io/effects/configuring-an-effect)
      - id: close_inventory
      - id: play_sound
        args:
          sound: block_anvil_use
          volume: 0.2
          pitch: 1.0
      - id: send_title
        args:
          title: "&a&lSuccess!"
          subtitle: "&fAdded &cReinforcement &fto your item."
    crafting: # The scroll item crafting
      enabled: true # If scroll item should be craftable
      recipe: # The actual recipe
        - "stick"
        - "iron_sword"
        - "stick"
        - "iron_sword"
        - "diamond"
        - "iron_sword"
        - "stick"
        - "iron_sword"
        - "stick"
      permission: "itemeffects.craft.reinforcement.swords" # A permissions one must have in order to craft (if crafting enabled)
```

### name

A formatted name for your holder (supports PlaceholderAPI placeholders).

### default-lore

A default lore which will be displayed on the item if you do not specify override lore in the `add` command.

### conflicts

A list of holder IDs that conflict with this one.

### requirements

A list of holder IDs that have to be applied to item before this one can be applied.

### effects

A list of [Libreforge effects](https://plugins.auxilor.io/effects/configuring-an-effect) a player will get on his
items with this holder.

### conditions

A list of [Libreforge conditions](https://plugins.auxilor.io/effects/configuring-a-condition) a player has to meet
to be able to use this holder.

### scrolls

A list of [Scrolls](Configuring-A-Scroll.md) configurations ([Scroll](Configuring-A-Scroll.md) being a drag and drop item to apply holder to the item in-game).

**Created your holder ? Now look at [Configuring The Scrolls](Configuring-A-Scroll.md)!**