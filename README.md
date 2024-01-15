# Home Assistant Blueprints
A small collection of Home Assistant Blueprints.

## Very simple and small test automation.
### Time / Weekday Action
A very small and simple automation for executing an action (or several) at a specific time on a selectable day of the week.

![Screenshot of the automation.](/images/screenshot_ha-blueprint_time-weekday.jpg)

Link for the Home Assistant Menu Import (Settings > Automations & Scenes > Blueprints .. Import Blueprint):
```
https://github.com/SvenKo/ha-blueprints/blob/main/src/ha-blueprint_time-weekday.yaml
```

## Battery
### Battery Check
An automatic process to check the battery states.

While looking for a blueprint to monitor the battery status of all devices, I found Sbyx automation. However, I was missing some information about it, and I wanted to slightly revise the option to select the day of the week, including a few minor changes. Therefore here is a revised version.
There are devices that monitor the status internally and simply set a switch to the status, and some that indicate the current value in percent. Both are taken into account in this automation.

When selecting the exclude, please be sure to use the entity.

![Screenshot of the automation.](/images/screenshot_ha-blueprint_battery-check.jpg)

When it comes to the action (I use the fantastic Pushover), you can choose whatever you want. However, it should be noted that Telegram, for example, cannot use an underscore. Therefore, please include a rewrite when outputting. As soon as the message is specified, the warning appears. This is absolutely ok, as normal input does not allow parentheses. Then simply copy the text into the appropriate field.

```
{{sensors|replace(\"_\",\" \")}} 
```

![Screenshot of the automation.](/images/screenshot_pushover.jpg)

Link for the Home Assistant Menu Import (Settings > Automations & Scenes > Blueprints .. Import Blueprint):
```
https://github.com/SvenKo/ha-blueprints/blob/main/src/ha-blueprint_battery-check.yaml
```
