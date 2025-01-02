# Timer light toggle

This blueprint creates an automation that toggles a light on/off when
a trigger event happens. (The trigger event is typically something
like a button press.) Rather than controlling the light directly, the
blueprint is parameterized by a "light on" script and a "light off"
script. It is designed to be used with the timer-light-on-with-retry
and timer-light-off-sooner scripts from this repository.
