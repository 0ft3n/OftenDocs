# Configuring A Scroll

A scroll is one of the most useful things you can find in ItemEffects.

Scrolls allow you to create unlimited craftable/buyable (through 3d party GUIs/plugins) in-game items that will allow
your players to upgrade their items with a simple drag-and-drop

Each [Holder](Configuring-A-Holder-IE.md) has `scrolls:` section in its config, that is exactly where scrolls
are configured:

```yaml
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

### scrolls

The starting point of the scroll list, that can be found in each holder config (/plugins/ItemEffects/holders/*.yml)

If you do not want any scrolls for the holder, set them to `scrolls: []`.

### id

The ID of a scroll (can contain `a-z0-9-_` characters).

### uses-slot

A boolean value (`true/false`) specifying if this scroll should take slot after being applied
(see [Configuring limits](Main-Config.md)).

### updatable-lore

A boolean value (`true/false`), which if set to true, makes the holder always display `default-lore`, so if you
update `default-lore` in the config, all existing items with this scroll applied will also have lore updated.

### targets

A list of [Targets](Configuring-targets.md) that this scroll should be applicable to.

### item

The [Items Lookup String](https://plugins.auxilor.io/all-plugins/the-item-lookup-system) specifying the base item
of the scroll.

### name

A string representing formatted name of the scroll item.

### lore

A list of strings representing the lore of the scroll item.

Supports custom local placeholder: `%usages%` to display how many usages the scroll item has left

### usages

A positive integer value representing how many usages each scroll item of this type would have (if you want one instance
of the scroll item to be applicable to more than one item before it breaks).

### apply-effects

A list of [Libreforge effects](https://plugins.auxilor.io/effects/configuring-an-effect) that will be triggered on the player once when he applies this scroll on the item.

### crafting

A section to configure craftability of the scroll.

### crafting.enabled

If this scroll should be craftable at all.

### crafting.recipe

A list of 9 [Item Lookup](https://plugins.auxilor.io/all-plugins/the-item-lookup-system) strings representing the actual
recipe of the scroll item

### crafting.permission

Is a section allowing you to restrict crafting recipe of a scroll by permission.

**Done configuring ? Now let's [Learn plugin commands and permissions](Commands-And-Permissions-IE.md)!**