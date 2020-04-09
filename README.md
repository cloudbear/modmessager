# modmessager

Limmy's mod messager aka alert system.

Original work by [Gantee](https://twitch.tv/gantee)

## How to use

### !alert

A moderator may issue an `!alert` command in the twitch to trigger the alert system to display the text following the command.

E.g. `!alert Here is an alert` displays the alert box with the text "HERE IS AN ALERT"

### Timers

Including a timer expression in braces in the alert message will produce a countdown starting at that time.

A timer expression is an integer followed by a time unit, e.g. 'seconds', 'minutes', 'hours'.

The timer expression will display as a countdown in hh:mm:ss.  The hours component will not display when it is zero and it will disappear when a timer that at an hour or more counts to below an hour.

Examples:  
`{1 hour}` -> `1:00:00`  
`{2 hours}` -> `2:00:00`  
`{90 minutes}` -> `1:30:00`  
`{30 minutes}` -> `30:00`  
`{1 minute}` -> `1:00`  
`{90 seconds}` -> `1:30`