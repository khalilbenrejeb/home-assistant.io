---
title: Switch
description: Instructions on how to set up your switches with Home Assistant.
ha_category:
  - Switch
ha_release: 0.7
ha_quality_scale: internal
ha_domain: switch
ha_platforms:
  - light
ha_codeowners:
  - '@home-assistant/core'
ha_integration_type: entity
related:
  - docs: /docs/configuration/customizing-devices/
    title: Customizing devices
  - docs: /dashboards/
    title: Dashboard
---

The **Switch** {% term integration %} manages the state of the switch entities and allows you to control them.

- Maintains a state per switch and a combined state `all_switches`.
- Registers actions `switch.turn_on`, `switch.turn_off`, and `switch.toggle` to control switches.

{% include integrations/building_block_integration.md %}

## The state of a switch entity

The state of a switch {% term entity %} can be either **On** or **Off**.

In addition, the entity can have the following states:

- **Unavailable**: The entity is currently unavailable.
- **Unknown**: The state is not yet known.

## Device class

{% include integrations/device_class_intro.md %}

 The following device classes are supported for switches:

- **None**: Generic switch. This is the default and doesn't need to be set.
- **outlet**: A switch for a power outlet.
- **switch**: A generic switch.

## Automation

The switch entity provides specific triggers and conditions to help you automate your devices.

### Triggers
You can use these triggers to start an automation based on the state of the switch.

- **Turned on**: Fires when the switch is toggled to the 'on' state.
- **Turned off**: Fires when the switch is toggled to the 'off' state.

```yaml
automation:
  trigger:
    - platform: device
      domain: switch
      entity_id: switch.living_room_light
      type: turned_on