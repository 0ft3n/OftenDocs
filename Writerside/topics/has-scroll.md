# has_scroll


Checks is specified [Scroll](Configuring-A-Scroll.md) is active for player.

## Example configuration

```yaml
conditions:
  - id: "has_scroll"
    args:
      holder: "reinforcement_swords" # The ID of the scroll to be searched for.
      slots: # A list of slots to search in for active scroll.
        - any
    # ...other config (e.g. conditions, filters, mutators, etc.)
```