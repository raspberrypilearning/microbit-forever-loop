Als je wilt dat je micro:bit en MakeCode projecten een activiteit de hele tijd achter elkaar uitvoert, heb je een lus nodig die dat herhaalt gedurende de hele tijd dat je code wordt uitgevoerd. Hiervoor kun je een `de hele tijd`{:class='microbitbasic'} lus gebruiken.

#### Waar kun je de 'de hele tijd' lus vinden

Alle nieuwe MakeCode projecten hebben standaard een `de hele tijd`{:class='microbitbasic'} blok, maar als je het per ongeluk verwijderd hebt, kun je het terugvinden in het menu `Basis`{:class='microbitbasic'} van de Toolbox.

<img src="images/forever-location.png" alt="The Basic menu with the `forever` block highlighted." width="350"/>

#### Hoe kun je een de hele tijd-lus gebruiken

Deze lus herhaalt de **hele tijd** zolang je project wordt uitgevoerd, keer op keer. Dus alle codeblokken die je in de hele tijd-lus plaatst, worden uitgevoerd elke keer als de lus rondgaat.

Bijvoorbeeld, een `de hele tijd`{:class='microbitbasic'} lus wordt gebruikt om geluiden af te spelen in het muziekspeler project.

```microbit
basic.forever(function () {
    let deuntje = 0
    if (deuntje == 1) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Dadadadum), music.PlaybackMode.UntilDone)
        basic.showIcon(IconNames.Duck)
    } else if (deuntje == 2) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Punchline), music.PlaybackMode.UntilDone)
    } else if (deuntje == 3) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Birthday), music.PlaybackMode.UntilDone)
    } else if (deuntje == 4) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Baddy), music.PlaybackMode.UntilDone)
    }
})
```

Je hebt ook een de hele tijd lus gebruikt om te controleren of er bewegingen waren in het Slaap-monitor project.

```microbit
let rustPositie = 0
let bewegingen = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < rustPositie - 10 || input.rotation(Rotation.Roll) > rustPositie + 10) {
        bewegingen += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        rustPositie = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

In beide projecten had je delen code nodig die moesten blijven herhalen, en een `de hele tijd`{:class='microbitbasic'} lus is daar perfect voor.
