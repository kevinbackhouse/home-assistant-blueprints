# Timer light on with retry

This blueprint creates a script that switches on a light and its
associated countdown timer. Useful for controlling lights with the
strategy described in [this video](https://youtu.be/SuLPMxQUv0Q). You
need to create one [timer](https://www.home-assistant.io/integrations/timer/)
for each light. The blueprint is parameterized by the light and the
timer. At runtime, the generated script takes a "duration" parameter,
which determines how long the light will stay on.

The script does nothing if the light is already on with a sufficiently
long timer set. For example, if you call the script twice in quick
succession, first with a duration of 30 seconds and second with a
duration of 15 seconds, then the second call will do nothing. But if,
for example, there are only a few seconds left on the timer then the
second call will restart the timer from 15 seconds. This means that
multiple automations can trigger the same light. Whichever automation
requests the longest duration wins.

If the light is already on, but the timer isn't running, then that's
treated as equivalent to an infinite duration timer, so the script
does nothing. That's so that when somebody switches a light on
manually with the app then it will stay on permanently until they
manually switch it back off.

This blueprint generates a script, which means that it does not contain
any triggers. The intention is that you call the script from a separate
automation.

Note: this blueprint only handles switching on the light. A separate
automation is needed to switch the light off when the timer finishes.
