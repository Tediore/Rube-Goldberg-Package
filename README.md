# Rube Goldberg Package
This is a Home Assistant version of a Rube Goldberg machine. It consists of the following:
- 8 automations
- 1 `input_text`
- 1 `input_number`
- 1 `input_select`
- 1 `input_datetime`
- 10 `input_boolean` (also known as `flippy_boi`)
- 1 timer
- 1 script

When I enable the starting automation and turn on the dining room light, the following happens:<br>
**[1.]** All the other automations turn on.<br>
**[2.]** An `input_select` is changed to `On!`<br>
**[3.]** ...which triggers an `input_number` to be set to the brightness of the light<br>
**[4.]** ...which triggers an `input_text` to be changed to the value of the `input_number`<br>
**[5.]** ...which triggers a 5-second timer to start<br>
**[6.]** ...which, when completed, triggers an `input_datetime` to be set to the time the timer finished<br>
**[7.]** ...which triggers `input_boolean` 1 to turn on<br>
**[8.]** ...which triggers `input_boolean` 2 to turn on<br>
...<br>
**[16.]** ...which triggers `input_boolean` 10 to turn on<br>
**[17.]** ...which triggers the light to turn back off and resets everything.
