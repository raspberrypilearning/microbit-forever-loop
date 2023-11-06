If you want your micro:bit and MakeCode projects to repeatedly do something, you will need a loop that repeats for the whole time your code is running. For this, you can use a `forever`{:class='microbitbasic'} loop. 

#### Where to get a forever loop

All new MakeCode projects come with a `forever`{:class='microbitbasic'} block by default, but if you delete it you can find it again in the `Basic`{:class='microbitbasic'} menu of the Toolbox. 

<img src="images/forever-location.png" alt="The Basic menu with the `forever` block highlighted." width="350"/>

#### How to use the forever loop

This loop will repeat the **whole time** your project is running, again and again. So any code blocks you put inside the forever loop will run everytime the loop goes around. 

For example, a `forever`{:class='microbitbasic'} loop is used to play sounds in the Music player project.

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

You also used a forever loop to check for movement in the Sleep tracker project.

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

In both these projects, you needed sections of code to keep on repeating, and a `forever`{:class='microbitbasic'} loop is perfect for that.
