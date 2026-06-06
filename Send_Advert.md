#  Advert Trigger
Revised and simplified: The adverts on Companions are mostly forgotten or done infrequently but in Home Assistant we can automate them. But lets do this modest because we really do not need an advert for a good working Mesh. With the introduction of region scope we can now also limit the distribution of an advert in dense Meshcore Areas. Good option is the region and not do this nationwide.
Here is my version of this automation:

```
alias: MeshCore - Advert Trigger
description: Sends a MeshCore advert when desired with the proper region/scope
triggers:
  - trigger: time
    at: "06:02:00"
    weekday: sat
    id: TIME
conditions: []
actions:
  - action: meshcore.execute_command
    data:
      command: set_flood_scope <region>
  - action: meshcore.execute_command
    data:
      command: send_advert true
mode: single
```
Please change at, weekday and `<region>` to your desired values.
