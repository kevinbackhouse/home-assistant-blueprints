# Timer light off sooner

This blueprint creates a script that reduces the remaining time on a
countdown timer associated with a light, so that the light will be
switched off sooner. Useful for controlling lights with the strategy
described in [this video](https://youtu.be/SuLPMxQUv0Q). You need to
create one [timer](https://www.home-assistant.io/integrations/timer/)
for each light. The blueprint is parameterized by the light and the
timer. At runtime, the generated script takes a "duration" parameter,
which determines how long the light will stay on. It also takes a
"force" parameter, which tells the script to switch the light off even
if the countdown timer isn't running. (If the light is on, but the
timer isn't running, it means that somebody switched it on manually in
the home assistant app.)
