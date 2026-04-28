---
title: Lock
description: Instructions on how to set up your locks with Home Assistant.
ha_category:
  - Lock
ha_release: 0.7
ha_quality_scale: internal
ha_domain: lock
ha_codeowners:
  - '@home-assistant/core'
ha_integration_type: entity
related:
  - docs: /docs/configuration/customizing-devices/
    title: Customizing devices
  - docs: /dashboards/
    title: Dashboard
---

The **Lock** {% term integration %} manages the state of the lock entities and allows you to control them.

{% include integrations/building_block_integration.md %}

## The state of a lock entity

The state of a lock {% term entity %} can be one of the following:

- **Locked**: The lock is secured.
- **Unlocked**: The lock is open.
- **Locking**: The lock is in the process of securing.
- **Unlocking**: The lock is in the process of opening.
- **Jammed**: The lock mechanism is stuck.
- **Unavailable**: The entity is currently unavailable.
- **Unknown**: The state is not yet known.

## Automation

The lock entity provides specific triggers and conditions to help you automate your security.

### Triggers
You can use these triggers to start an automation based on the lock's activity.

- **Locked**: Fires when the lock is secured.
- **Unlocked**: Fires when the lock is opened.
- **Opened**: Fires when the door is physically opened (if supported).
- **Jammed**: Fires when the lock mechanism fails to engage.

```yaml
automation:
  trigger:
    - platform: device
      domain: lock
      entity_id: lock.front_door
      type: jammed