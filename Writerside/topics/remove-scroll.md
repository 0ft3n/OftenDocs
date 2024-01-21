# remove_scroll

**Triggered effect**

Removes specified [Scroll](Configuring-A-Scroll.md) from the item.

## Example configuration

```yaml
effects:
  - id: "remove_scroll"
    args:
      scroll: "reinforcement_swords" # The ID of the scroll to be removed.
    # ...other config (e.g. conditions, filters, mutators, etc.)
```