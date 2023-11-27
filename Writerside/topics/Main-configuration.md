# Main configuration

Here's how the plugins `config.yml` looks like:

## Default main config

```yaml
show-debug: false

bag:
  name: "&6%player%&7's drop"
  color: "6"
  item: "diamond_block"
  open-sound: "block_amethyst_cluster_break"
```

### show-debug

Allowed values: `true/false`

If debug output should be enabled in console (do not set this to true unless I ask you to)

### bag

The default bag config.

Each drop has its personal bag config option, but if not present - then this default bag is used
Drops with identical bags are combined if both get produced.

#### name

The name of bag item, use `%player%` to insert the drop owner name

### color
allowed values: `1, 2, 3, 4, 5, 6, 7, 8, 9, 0, a, e, f, c, b`

The color of bag outline (supports all colors that vanilla glowing supports).

### item

The [Item lookup string](https://plugins.auxilor.io/all-plugins/the-item-lookup-system) for bag item

### open-sound

Allowed values: [Spigot sounds](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Sound.html)

A sound that is played when player opens the bag (left clicks it)