Μπορείς να χρησιμοποιήσεις τα μπλοκ `αληθές`{:class='microbitlogic'} και `ψευδές`{:class='microbitlogic'} για να ελέγξεις (σημαία) όταν έχει συμβεί κάτι στον κώδικά σου.

Στο έργο του Μετρητή ήχου, βεβαιώσου ότι ο θόρυβος του συναγερμού δεν προσθέτει στο ήδη θορυβώδες περιβάλλον.

Το έκανες αυτό ορίζοντας τη μεταβλητή `συναγερμός`{:class='microbitvariables'} σε `ψευδές`{:class='microbitlogic'} όταν ξεκίνησε ο κώδικάς σου.

```microbit
let alarm = false
```

Έλεγξες ότι ο συναγερμός δεν ήταν ήδη ενεργός εάν το επίπεδο ήχου ήταν πολύ υψηλό.

Εάν ο συναγερμός δεν ήταν ενεργός και το επίπεδο ήχου ήταν πολύ υψηλό, ορίζεις τη μεταβλητή `συναγερμός`{:class='microbitvariables'} σε `αληθές`{:class='microbitlogic'}.

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

Ρυθμίζεις ξανά το συναγερμό σε `ψευδές`{:class='microbitlogic'} όταν πατήσεις το λογότυπο αφής.

```microbit
let alarm = false
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    alarm = false
})
```

Αυτό σας επιτρέπει να ενεργοποιείτε το συναγερμό μόνο εάν δεν έχει ήδη ενεργοποιηθεί.

- Μπορείς να βρεις τα μπλοκ `αληθές`{:class='microbitlogic'}, `ψευδές`{:class='microbitlogic'} και `όχι`{:class='microbitlogic'} στο μενού `Λογική`{:class='microbitlogic'} στην Εργαλειοθήκη.
