input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    randomNumber = randint(0, 4)
    if (randomNumber == 4) {
        basic.showString("NO!")
    } else if (randomNumber == 3) {
        basic.showString("Nope!")
    } else if (randomNumber == 2) {
        basic.showString("Never!")
    } else if (randomNumber == 1) {
        basic.showString("Not really")
    } else {
        basic.showString("IDK")
    }
    basic.showNumber(8)
})
let randomNumber = 0
basic.showString("Ask a question!")
basic.showNumber(8)
