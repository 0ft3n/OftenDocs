# Configuring a drop

To create your very own custom drop, head to your `plugins/RPGDrops/drops/` folder, where you can create a new file,
name it `a-z,0-9,-_` lowercase and put the actual drop options inside it.

You can use the `plugins/RPGDrops/drops/_example.yml` drop for reference when creating a new drop.

Let's dive into the example config to see what it consists of:

## Example config

```yaml
id: example_drop_3
use-bag: true
color: "a"
items:
  - "stone 12 name:\"&6Hey there\""
  - "dirt 10 name:\"&dVery useful dirt :3\""
mobs:
  - "zombie::100.0"
  - "spawner_skeleton::50.5"
blocks:
  - "stone::100.0"
levelledmobs-minimum-level: 10
fishing-chance: 35.0
reward-commands:
  - "say %player% got an example reward!"
velocity-multiplier: 2.5
trail: "flame"
trail-duration: 100
trail-amount: 3
minimum-damage-percent: 0.0
telekinetic: true
conditions: []
not-met-effects: []
bag:
  name: "&6%player%&7's drop (custom bag)"
  color: "3"
  item: "diamond_block"
  open-sound: "block_amethyst_cluster_break"
```

### id

The actual drop ID, naming rules are at the start of this page, you use the drop ID when you summon it with a command
or reference it in the effects (TODO).

### use-bag
Allowed values: `true/false`

If the drop should be put in bag, or just be directly thrown out as an item.

**Ignored if telekinetic is set to true**

### color
allowed values: `1, 2, 3, 4, 5, 6, 7, 8, 9, 0, a, e, f, c, b`

The color of drop outline (supports all colors that vanilla glowing supports).

### items

A list of [Item lookup strings](https://plugins.auxilor.io/all-plugins/the-item-lookup-system) specifying items a player can get from that drop.

### mobs

A list of [Entity lookup](https://plugins.auxilor.io/all-plugins/the-entity-lookup-system) strings combined with chances like `mob::chance`, specifying chances for a certain
mob to produce that certain drop when killed.

### blocks

A list of block materials (`oraxen:id` for [Oraxen blocks](https://oraxen.com/), `itemsadder:id`
for [ItemsAdder blocks](https://itemsadder.devs.beer/)) combined with chances like `mob::chance`, 
specifying chances for a certain block to produce that certain drop when broken.

### levelledmobs-minimum-level

Requires [LevelledMobs](https://www.spigotmc.org/resources/levelledmobs.74304/)!

A minimal LevelledMobs level of a killed mob for it to produce this drop.

### fishing-chance

A double value(`0.0-100.0`) specifying the chance for this drop to be produced during fishing.

### reward-commands

A list of command strings to be executed from console when a player gets this drop
(Use `%player%` to get a player name into the command).

### velocity-multiplier

A double value specifying the multiplier to be applied to the bag/drop velocity when they 
drop (check out the [Showcase](Showcase.md) to get the idea of how does it look like).

### trail

Allowed values: [Spigot particles](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Particle.html)

A particle to be used for the bag/drop trail.

### trail-duration

A number of ticks specifying how long trail particle should be played when drop is out.

### trail-amount

A number of particles per-tick to spawn in trail.

### minimum-damage-percent

A double value(`0.0-100.0`) specifying how much damage in max health % a player has to deal to the mob to get a chance
for this drop.

### telekinetic
Allowed values: `true/false`

If the drop should be put directly in players inventory instead of the ground.

**Overrides the use-bag: true/false setting**

### conditions

A list of [Libreforge conditions](https://plugins.auxilor.io/effects/configuring-a-condition) a player has to meet
to be able to get this drop,

### not-met-effects

A list of [Libreforge effects](https://plugins.auxilor.io/effects/configuring-an-effect) to be performed if a player
tries to get this drop, but does not meet conditions from the previous config option.

### bag

A custom bag configuration for this drop (see [Bag configuration](Main-configuration.md#bag))