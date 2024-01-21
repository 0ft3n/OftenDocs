# Commands And Permissions

## Commands:

### /itemeffects - Main command

Permission: 'itemeffects.command.itemeffects'

The main plugin command, does nothing on itself

### /itemeffects reload - Reload configuration

Permission: 'itemeffects.command.reload'

Reload all plugin configurations

### /itemeffects add <holder> <slot> <lore> - Add a holder to item in main hand

Permission: 'itemeffects.command.add'

* \<holder> - An ID of the holder to be added (see [Drop ID](Configuring-a-drop.md#id)).
* \<slot> - Slot for holder to work in (Available options: `mainhand`, `offhand`, `hands`,
`armor`, `helmet`, `chestplate`, `leggings`, `boots`, `any`).
* \<lore> - If you want to override the Default lore of the holder, you can specify it in the command, it supports PlaceholderAPI placeholder and updates dynamically. You can also add multiline lore by separating new lines with `/nl` sequence.

Add a holder to the item in main hand

### /itemeffects give <player> <scroll> <amount> - Give player certain scroll items

* \<player> - The name of an online player to give scrolls to.
* \<scroll> - An ID of the scroll to be added (see [Scroll ID](Configuring-A-Scroll.md#id)).
* \<amount> - Amount of scroll items to give.

Give player some scroll items (As alternative to crafting).