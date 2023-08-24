# Custom Card - Banner

## Credits
- Author: Paul Ward - 2023
- Version: 1.0.0
- Credits to: Everything Smart Home [ESH welcome card](https://github.com/UI-Lovelace-Minimalist/UI/tree/main/custom_cards/custom_card_esh_welcome)
- Credits to: [welcome scenes card](https://ui-lovelace-minimalist.github.io/UI/usage/cards/card_welcome_scenes/) as the basis

## Description
This is a welcome card based on the work done by Everything Smart Home on his welcome card.  The card itself is designed to be used by room or zone pages that are linked from a main or home page.

The major differences are:
 * removed navigation buttons,
 * added chips for scene selection, light brightness presets, and occupancy notification,
 * replaced the 'collapse' button with a 'back' button that can navigate to a specified page,
 * replaced temperature/weather button with a chip that shows the current page title,
 * Removed newline in welcome message.

If the card is linked to a light entity, that entity will also be shown in the card.

## Variables

| Variable                                      | Default | Required | Description                                                                                          |
|-----------------------------------------------|---------|:--------:|------------------------------------------------------------------------------------------------------|
| `custom_card_asmodai_banner_back_path`        |         | Yes      | Path to navigate to when 'back' is pressed.                                                          |
| `custom_card_asmodai_banner_name`             |         | Yes      | Name displayed in the title chip.                                                                    |
| `custom_card_asmodai_banner_icon`             |         | Yes      | Icon displayed in the title chip.                                                                    |
| `custom_card_asmodai_banner_light_entity`     |         | No       | Light entity to show in the card.                                                                    |
| `custom_card_asmodai_banner_scene_filter`     |         | No       | Filter used to determine which scenes show in the scene selection.                                   |
| `custom_card_asmodai_banner_scene_exclude`    |         | No       | Filter used to exclude scenes from the scene selection.  This must be non-empty if a filter is used. |
| `custom_card_asmodai_banner_occupancy_entity` |         | No       | Entity used to determine whether the room or zone is occupied.                                       |

## Usage
```yaml
  - type: "custom:button-card"
    template: "card_asmodai_banner"
    variables:
      custom_card_asmodai_banner_back_path: "home"
      custom_card_asmodai_banner_name: "Hallway"
      custom_card_asmodai_banner_icon: 'mdi:home-floor-g'
      custom_card_asmodai_banner_light_entity: light.room_hallway
      custom_card_asmodai_banner_scene_filter: "scene.hallway*"
      custom_card_asmodai_banner_scene_exclude: "scene.hallway_nope*"
      custom_card_asmodai_banner_occupancy_entity: binary_sensor.esp1_hallway_occupancy
```

