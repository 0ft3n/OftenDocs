# has_holder

Checks is specified [Holder](Configuring-A-Holder-IE.md) is active for player.

## Example configuration

```yaml
conditions:
  - id: "has_holder"
    args:
      holder: "reinforcement" # The ID of the holder to be searched for.
      slots: # A list of slots to search in for active holder.
        - any
    # ...other config (e.g. conditions, filters, mutators, etc.)
```