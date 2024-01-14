# Configuring A Holder

To create your very own custom holder, head to your `plugins/ItemEffects/holders/` folder, where you can create a new file,
name it `a-z,0-9,-_` lowercase and put the actual holder options inside it.

You can use the `plugins/ItemEffects/holders/_example.yml` holder for reference when creating a new holder.

Let's dive into the example config to see what it consists of:

## Example config

```yaml
name: "&c&lPower"

default-lore:
  - ""
  - "&cWhile above 50% health,"
  - "&cdeal 3 additional damage per hit"

effects:
  - id: add_damage
    args:
      damage: 3
    triggers:
      - melee_attack

conditions:
  - id: above_health_percent
    args:
      percent: 50
```

### name

A formatted name for your holder (supports PlaceholderAPI placeholders).

### default-lore

A default lore which will be displayed on the item if you do not specify override lore in the `add` command

### effects

A list of [Libreforge effects](https://plugins.auxilor.io/effects/configuring-an-effect) a player will get on his
items with this holder.

### conditions

A list of [Libreforge conditions](https://plugins.auxilor.io/effects/configuring-a-condition) a player has to meet
to be able to use this holder.