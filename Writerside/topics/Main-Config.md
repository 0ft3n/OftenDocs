# Main Config

Main config.yml file of ItemEffects has a few global options for the plugin:

```yaml
default-limit: 1 # A limit that is active if none of specified in `limits` do not match the case
limits: # A list of configured limits
  - items: # A list of items that this limit is applied to
      - diamond_sword name:"&4Custom Sword"
    limit: 2 # The actual limit (2 holders per item)
  - items: # A list of items that this limit is applied to
      - diamond_sword name:"&4Custom Sword"
    limit: 3 # The actual limit (3 holders per item)
    permission: "itemeffects.customsword.extended" # A permission player has to have to use this limit
```

Limits configuration is a way to restrict how many scrolls can be applied to each item

### default-limit

A default limit to be used when none of the `limits:` limits are applicable.

### limits

A list of configured limits per-item groups/permission-based

### items

A list of [Items Lookup](https://plugins.auxilor.io/all-plugins/the-item-lookup-system) strings specifying the items
this limit is applicable to

### limit

Is the actual limit per item

### permission

Is a permission one has to have to be applicable for this limit (can be used to increase limits as a donor perk)


**Configured the plugin ? Now it's time to [Create your first holder](Configuring-A-Holder-IE.md)!**