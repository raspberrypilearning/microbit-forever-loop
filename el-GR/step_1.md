Εάν θέλεις τα έργα σου micro:bit και MakeCode να κάνουν επανειλημμένα κάτι, θα χρειαστείς έναν βρόχο που επαναλαμβάνεται καθ' όλη τη διάρκεια της εκτέλεσης του κώδικά σου. Γι' αυτό, μπορείς να χρησιμοποιήσεις έναν βρόχο `για πάντα`{:class='microbitbasic'}.

#### Πού να βρεις ένα βρόχο για πάντα

Όλα τα νέα έργα του MakeCode διαθέτουν ένα μπλοκ`για πάντα`{:class='microbitbasic'} από προεπιλογή, αλλά αν το διαγράψεις, μπορείς να το βρεις ξανά στο μενού `Βασικά`{:class='microbitbasic'} της Εργαλειοθήκης.

<img src="images/forever-location.png" alt="The Basic menu with the `forever` block highlighted." width="350"/>

#### Πώς να χρησιμοποιήσεις έναν βρόχο για πάντα

Αυτός ο βρόχος θα επαναλαμβάνεται **όλη την ώρα** που εκτελείται το έργο σου, ξανά και ξανά. Έτσι, όλα τα μπλοκ κώδικα που βάζεις μέσα στον βρόχο για πάντα θα εκτελούνται κάθε φορά που ο βρόχος επαναλαμβάνεται.

Για παράδειγμα, ένας βρόχος `για πάντα`{:class='microbitbasic'} χρησιμοποιείται για την αναπαραγωγή ήχων στο έργο του προγράμματος αναπαραγωγής Μουσικής.

```microbit
basic.forever(function () {
    let μελωδία = 0
    if (μελωδία == 1) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Dadadadum), music.PlaybackMode.UntilDone)
        basic.showIcon(IconNames.Duck)
    } else if (μελωδία == 2) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Punchline), music.PlaybackMode.UntilDone)
    } else if (μελωδία == 3) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Birthday), music.PlaybackMode.UntilDone)
    } else if (μελωδία == 4) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Baddy), music.PlaybackMode.UntilDone)
    }
})
```

Χρησιμοποίησες επίσης έναν βρόχο για πάντα για να ελέγξεις για κίνηση στο έργο Παρακολούθησης ύπνου.

```microbit
let restingPosition = 0
let κινήσεις = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < restingPosition - 10 || input.rotation(Rotation.Roll) > restingPosition + 10) {
        κινήσεις += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        restingPosition = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

Και στα δύο αυτά έργα, χρειάστηκες τμήματα κώδικα να συνεχίζουν να επαναλαμβάνονται και ένας βρόχος `για πάντα`{:class='microbitbasic'} είναι τέλειος γι' αυτό.
