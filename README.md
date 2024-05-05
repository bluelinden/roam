# Roam for Home Assistant
Home Assistant integration providing activity-based automations that you don't need to worry about.

## Ideas
* Adjacent areas
  * Pair areas up with joining areas, and have lights turn on or off as you move between rooms or floors of your house.
* Stateful, declarative automation
  * People don't think of smart homes as needing a list of steps to do, they just want a thing to be on or off, high or low. Imperative automations, although easier for developers to think about, take a level of mental gymnastics and troubleshooting skills that regular people don't want to use when they want to control their lights. So Roam provides them with a state machine.
    * When X happens, Y should be in a specific state. If Y can't be made to match the state, then emit an error and explain what happened.
    * When X stops happening, Y should go back to the way it was before, unless otherwise specified.
    * Everything has a "canonical" state and the system should default back to it.
    * In situations where mutable state isn't desired, when no one has intentionally modified the system's state, everything should mirror the canonical state.
    * To escape the canonical state, the user just needs to modify anything about any state, and the system will cede control until the user cedes control back.
