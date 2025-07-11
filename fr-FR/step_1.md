Tu peux utiliser les blocs `vrai`{:class='microbitlogic'} et `faux`{:class='microbitlogic'} pour vérifier (drapeau) quand quelque chose s'est passé dans ton code.

Dans le projet Sonomètre, tu as veillé à ce que le bruit de l'alarme ne rendait pas l'endroit encore plus bruyant.

Tu as fait cela en définissant la variable `alarme`{:class='microbitvariables'} à `faux`{:class='microbitlogic'} lorsque ton code a démarré.

```microbit
let alarm = false
```

Tu as vérifié que l'alarme n'était pas déjà active si le niveau sonore était trop élevé.

Si l'alarme n'était pas active et que le niveau sonore était trop élevé, tu as défini la variable `alarme`{:class='microbitvariables'} à `vrai`{:class='microbitlogic'}.

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

Tu remets l'alarme sur `faux`{:class='microbitlogic'} lorsque le logo tactile est pressé.

```microbit
let alarm = false
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    alarm = false
})
```

Cela te permet de déclencher l'alarme uniquement si elle n'a pas déjà été déclenchée.

- Tu peux trouver les blocs `vrai`{:class='microbitlogic'}, `faux`{:class='microbitlogic'} et `non`{:class='microbitlogic'} dans le menu `Logique`{:class='microbitlogic'} de ta boîte à outils.
