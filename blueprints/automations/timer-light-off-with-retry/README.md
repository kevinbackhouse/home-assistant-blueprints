# Timer light off with retry

This blueprint creates an automation that switches a light off when a
countdown timer finishes. Useful for controlling lights with the strategy
described in [this video](https://youtu.be/SuLPMxQUv0Q). You need to
create one [timer](https://www.home-assistant.io/integrations/timer/) for
each light. The blueprint is parameterized by the light and the timer.

Note: this blueprint only handles switching off the light. A separate
automation is needed to start the countdown timer when the light is
switched on.
