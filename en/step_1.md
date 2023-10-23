You can use `true`{:class='microbitlogic'} and `false`{:class='microbitlogic'} blocks to check (flag) when something has happened in your code.

In the Sound meter project, you made sure the alarm noise did not add to the already noisy environment.

You did this by setting the `alarm`{:class='microbitvariables'} variable to `false`{:class='microbitlogic'} when your code started.

```microbit
let alarm = false
```

You then checked that the alarm was not set to true if the sound level was too high before setting off the alarm. 

You then set it to `true`{:class='microbitlogic'} when the alarm sounded. 

```microbit
let alarm = false
loops.everyInterval(500, function () {
    let maximum = 0
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("Sound level", input.soundLevel()))
    if (input.soundLevel() > maximum && !(alarm)) {
        music.play(music.builtinPlayableSoundEffect(soundExpression.mysterious), music.PlaybackMode.UntilDone)
        alarm = true
    }
})
```

You set the alarm back to `false`{:class='microbitlogic'} when the touch logo is pressed.

```microbit
let alarm = false
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    alarm = false
})
```

This let you only trigger the alarm if it was not already triggered.

- You can find the `true`{:class='microbitlogic'}, `false`{:class='microbitlogic'}, and `not`{:class='microbitlogic'} blocks in the `Logic`{:class='microbitlogic'} menu in your Toolbox.
