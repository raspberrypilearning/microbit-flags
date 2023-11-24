Je kunt `waar`{:class='microbitlogic'} en `onwaar`{:class='microbitlogic'} blokken gebruiken om te controleren (markeren) of er iets in je code is gebeurd.

In het project Geluidsmeter heb je ervoor gezorgd dat het alarmgeluid de toch al luidruchtige omgeving niet verergerde.

Je hebt dit gedaan door de `alarm`{:class='microbitvariables'} variabele op `onwaar`{:class='microbitlogic'} in te stellen toen je code begon.

```microbit
let alarm = false
```

Je hebt gecontroleerd of het alarm niet al actief was als het geluidsniveau te hoog was.

Als het alarm niet actief was en het geluidsniveau te hoog was, zette je de `alarm`{:class='microbitvariables'} variabele op `waar`{:class='microbitlogic'}.

```microbit
let alarm = false
loops.everyInterval(500, function () {
    let maximum = 0
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("Geluidsniveau", input.soundLevel()))
    if (input.soundLevel() > maximum && !(alarm)) {
        music.play(music.builtinPlayableSoundEffect(soundExpression.mysterious), music.PlaybackMode.UntilDone)
        alarm = true
    }
})
```

Je hebt het alarm teruggezet naar `onwaar`{:class='microbitlogic'} wanneer het logo werd aangeraakt.

```microbit
let alarm = false
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    alarm = false
})
```

Hierdoor kun je het alarm alleen activeren als het nog niet is geactiveerd.

- Je kunt de `waar`{:class='microbitlogic'}, `onwaar`{:class='microbitlogic'} en `niet`{:class='microbitlogic'} blokken vinden in het `Logisch`{:class='microbitlogic'} menu in je Toolbox.
