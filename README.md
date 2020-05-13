# modmessager

[Limmy](https://twitch.tv/limmy)'s mod messager aka alert system.

Original work by [Gantee](https://twitch.tv/gantee)

## How to use

### Setting it for your channel

To set the messager to watch your channel, find the following code in the top of the main javascript block in `modmessager.htm`:

```javascript
    // Define configuration options
    const opts = {
        channels: [
          "limmy"
        ]
    };
```

Change "limmy" to the name of your channel, i.e. what comes after `twitch.tv/` in the URL.

### Adding to OBS

1. Download the source code and put it in its own folder somewhere with your streaming resources.
2. Add a browser source. Name it what you like.
3. Set it to local file and browse to modmessager.htm
4. Set width and height to the width and height of your stream.
5. Uncheck 'Shutdown source when not visible' and 'Refresh browser when scene becomes active'.

### Customisation

The styling of the alert is specified in CSS near the top of the htm document.

Change the following CSS property to customise the corresponding part of the alert.  Don't change properties not listed here unless you know what you're doing.

| CSS Selector    | Property          | Affects          | Type (Recommended)            | Example  |
|:----------------|:------------------|:-----------------|:------------------------------|:---------|
| #message        | font-family       | Font             | Text (name of font)           | `Arial`, `'Open Sans Condensed'`, `'Bahnschrift Regular'` |
|                 | font-weight       | Boldness         | Number or CSS weight name     | `400`, `900`, `bold`, `bolder`  |
|                 | color             | Text colour      | Hex or CSS colour name        | `#FFFFFF`, `white`, `#FF0000`, `red`  |
|                 | font-size         | Text size        | Number with points or pixels  | `60px`, `48pt`  |
| #modmessagebox  | bottom            | Gap below box    | Number with pixels or 0       | `0`, `0px`, `5px`, `15px`  |
|                 | left              | Gap left of box  | Number with pixels or 0       | `0`, `0px`, `5px`, `15px`  |
|                 | height            | Height of box    | Number with pixels            | `82px`  |
|                 | background-color  | Box colour       | Hex or CSS colour name        | `#00FF00`, `green`, `#000000`, `black`  |

### !alert

A moderator may issue an `!alert` command in the twitch to trigger the alert system to display the text following the command.

E.g. `!alert Here is an alert` displays the alert box with the text "HERE IS AN ALERT"

### Timers

Including a timer expression in braces anywhere in the alert message will produce a countdown in that position in the message, starting at that time.

A timer expression is an integer or decimal number followed by a time unit, e.g. 'seconds', 'minutes', 'hours'.

The timer expression will display as a countdown in hh:mm:ss.  The hours component will not display when it is zero and it will disappear when a timer that at an hour or more counts to below an hour.

Timer expression examples:  
`{1 hour}` -> `1:00:00`  
`{2 hours}` -> `2:00:00`  
`{1.5 hours}` -> `1:30:00`  
`{90 minutes}` -> `1:30:00`  
`{30 minutes}` -> `30:00`  
`{2.5 minutes}` -> `2:30`  
`{1 minute}` -> `1:00`  
`{90 seconds}` -> `1:30`

Alert example using the timer:  
`!alert Mudrunner for {90 minutes} and then Warzone` will display `MUDRUNNER FOR 1:30:00 AND THEN WARZONE`, which will then tick down, e.g. `MUDRUNNER FOR 1:29:59 AND THEN WARZONE`, and so on.

## Contributing

To report issues, use the issues tab and give a detailed report of the problem.  Include:

- what you were trying to do, including exact commands and parameters
- what you expected to happen
- what actually happened
- the streaming environment you were using (e.g. OBS, Streamlabs OBS, etc.)

To contribute code to the mod messager, fork the repo, develop your changes in a feature branch, and then make a pull request.

To be added as a contributor, so that you can develop on the main repo, request contributor status in the text of the pull request of a contribution.
