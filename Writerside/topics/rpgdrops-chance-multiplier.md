# rpgdrops_chance_multiplier
**Permanent effect**

Multiplies chance to get certain RPGDrops

## Example configuration

```yaml
effects:
  - id: "rpgdrops_chance_multiplier"
    args:
      drops: # A list of drop IDs for this multiplier to be applied to
        - "example"
        - "another_drop"
      multiplier: "%player_health%*0.1" # A multiplier to be applied to the chance
                    # (supports math expressions and placeholders!)
    # ...other config (e.g. conditions, filters, mutators, etc.)
```