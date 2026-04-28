---
title: Entity Naming and Organization
description: Guidance on the relationship between device names, entity names, and area names in Home Assistant.
---

In Home Assistant, naming is the key to a manageable smart home. This guide explains the relationship between **Areas**, **Devices**, and **Entities** to help you understand the naming model.

## The Naming Hierarchy

Home Assistant uses a structured approach to keep your dashboard organized:

1.  **Area**: The physical location (e.g., "Living Room").
2.  **Device**: The physical hardware (e.g., "Philips Hue Bulb").
3.  **Entity**: The specific sensor or control (e.g., `light.living_room_lamp`).



### Relationship between Device and Area
When you assign a **Device** to an **Area**, Home Assistant suggests names for the entities associated with it. 

- **Best Practice**: Name your Device clearly (e.g., "Ceiling Light"), then assign it to an Area ("Kitchen"). Home Assistant will automatically handle the unique Entity IDs.

## The New Naming Model
The platform is migrating toward a model where entity names do not need to repeat the device name.

- **Old Model**: Device "Kitchen Light", Entity "Kitchen Light Power".
- **New Model**: Device "Kitchen Light", Entity "Power".

When migrating, you should rename your **Devices** first. If a device is named "Multi-sensor," its entities will automatically be grouped under that device context in the UI.

## Renaming Guidelines
- **Avoid Redundancy**: If a device is in the "Kitchen" area, don't name the device "Kitchen Light." Just name it "Main Light" and assign it to the Kitchen.
- **Friendly Names vs. Entity IDs**: You can change the "Friendly Name" (what you see in the UI) without breaking your automations that rely on the "Entity ID" (the unique string used in code).