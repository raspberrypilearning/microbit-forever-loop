Si tu souhaites que tes projets micro:bit et MakeCode effectuent quelque chose de manière répétée, tu auras besoin d'une boucle qui se répète pendant toute la durée d'exécution de ton code. Pour cela, tu peux utiliser une boucle `toujours`{:class='microbitbasic'}.

#### Où trouver la boucle toujours

Tous les nouveaux projets MakeCode sont fournis avec un bloc `toujours`{:class='microbitbasic'} par défaut, mais si tu le supprimes, tu peux le retrouver dans le menu `Base`{:class='microbitbasic'} de la boîte à outils.

<img src="images/forever-location.png" alt="The Basic menu with the `forever` block highlighted." width="350"/>

#### Comment utiliser la boucle toujours

Cette boucle se répétera **toute la durée** d'exécution de ton projet, encore et encore. Ainsi, tous les blocs de code que tu places dans la boucle toujours s'exécuteront à chaque fois que la boucle fera une boucle.

Par exemple, une boucle `toujours`{:class='microbitbasic'} est utilisée pour lire des sons dans le projet Lecteur de musique.

```microbit
basic.forever(function () {
    let tune = 0
    if (tune == 1) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Dadadadum), music.PlaybackMode.UntilDone)
        basic.showIcon(IconNames.Duck)
    } else if (tune == 2) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Punchline), music.PlaybackMode.UntilDone)
    } else if (tune == 3) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Birthday), music.PlaybackMode.UntilDone)
    } else if (tune == 4) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Baddy), music.PlaybackMode.UntilDone)
    }
})
```

Tu as également utilisé une boucle toujours pour vérifier les mouvements dans le projet Suivi du sommeil.

```microbit
let restingPosition = 0
let movements = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < restingPosition - 10 || input.rotation(Rotation.Roll) > restingPosition + 10) {
        movements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        restingPosition = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

Dans ces deux projets, tu avais besoin de sections de code pour continuer à répéter, et une boucle `toujours`{:class='microbitbasic'} est parfaite pour cela.
