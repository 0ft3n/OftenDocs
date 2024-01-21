# add_scroll

**Triggered effect**

Adds specified [Scroll](Configuring-A-Scroll.md) to the item.

## Example configuration

```yaml
effects:
  - id: "add_scroll"
    args:
      scroll: "reinforcement_swords" # The ID of the scroll to be applied.
      override-targets: false # If set to true, effect will not check for the scroll target before applying.
    # ...other config (e.g. conditions, filters, mutators, etc.)
```