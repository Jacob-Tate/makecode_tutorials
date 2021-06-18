# Lemon Leak with Status Bars

## Introduction @unplugged

Let's make our lemon game a little more interesting by adding a health bar to the top of our lemon! By the end of this tutorial you should know how to use the status bar extension.

## Step One - Create the status bar

Take a peek into the new ``||statusbars: Status Bar||`` category! You'll need to grab ``||variables:set [statusbar] to create status bar sprite width [20] height [4] kind [Health]||``. Drag this to the end of the ``||loops: on start||`` container. 

If you find youself running low on room go ahead and move your blocks around makecode will expand itself for you automatically!

<hr/>

>> *Tip: The ``||statusbars:Status Bars||`` category is an __extension__ to see what else you can do using extensions, open a game in your gallery, click ``||statusbars:˅ Advanced||`` and choose ``||extension:Extensions||``*

```package
pxt-status-bar=github:jwunderl/pxt-status-bar#v0.4.1
```

```blocks
scene.setBackgroundColor(10)
let lemon = sprites.create(img`
    4 4 4 . . 4 4 4 4 4 . . . . . . 
    4 5 5 4 4 5 5 5 5 5 4 4 . . . . 
    b 4 5 5 1 5 1 1 1 5 5 5 4 . . . 
    . b 5 5 5 5 1 1 5 5 1 1 5 4 . . 
    . b d 5 5 5 5 5 5 5 5 1 1 5 4 . 
    b 4 5 5 5 5 5 5 5 5 5 5 1 5 4 . 
    c d 5 5 5 5 5 5 5 5 5 5 5 5 5 4 
    c d 4 5 5 5 5 5 5 5 5 5 5 1 5 4 
    c 4 5 5 5 d 5 5 5 5 5 5 5 5 5 4 
    c 4 d 5 4 5 d 5 5 5 5 5 5 5 5 4 
    . c 4 5 5 5 5 d d d 5 5 5 5 5 b 
    . c 4 d 5 4 5 d 4 4 d 5 5 5 4 c 
    . . c 4 4 d 4 4 4 4 4 d d 5 d c 
    . . . c 4 4 4 4 4 4 4 4 5 5 5 4 
    . . . . c c b 4 4 4 b b 4 5 4 4 
    . . . . . . c c c c c c b b 4 . 
    `, SpriteKind.Player)
controller.moveSprite(lemon)
// Prevent the lemon from leaving the screen
lemon.setStayInScreen(true)
info.startCountdown(30)
let statusbar = statusbars.create(20, 4, StatusBarKind.Health)
```

## Step Two - Attach status bar to lemon

If you try to play the game now you'll notice that the health bar is smack in the middle of our lemon and thats no good!
<hr/>
Go back into the ``||statusbars: Status Bar||`` category and grab ``||statusbars: attach [statusbar] to [mysprite]||`` placing it at the bottom of our ``||loops: on start||`` container.

Last we will fix that pesky error and set ``||variables: mySprite||`` to ``||variables: lemon||``!

```blocks
scene.setBackgroundColor(10)
let lemon = sprites.create(img`
    4 4 4 . . 4 4 4 4 4 . . . . . . 
    4 5 5 4 4 5 5 5 5 5 4 4 . . . . 
    b 4 5 5 1 5 1 1 1 5 5 5 4 . . . 
    . b 5 5 5 5 1 1 5 5 1 1 5 4 . . 
    . b d 5 5 5 5 5 5 5 5 1 1 5 4 . 
    b 4 5 5 5 5 5 5 5 5 5 5 1 5 4 . 
    c d 5 5 5 5 5 5 5 5 5 5 5 5 5 4 
    c d 4 5 5 5 5 5 5 5 5 5 5 1 5 4 
    c 4 5 5 5 d 5 5 5 5 5 5 5 5 5 4 
    c 4 d 5 4 5 d 5 5 5 5 5 5 5 5 4 
    . c 4 5 5 5 5 d d d 5 5 5 5 5 b 
    . c 4 d 5 4 5 d 4 4 d 5 5 5 4 c 
    . . c 4 4 d 4 4 4 4 4 d d 5 d c 
    . . . c 4 4 4 4 4 4 4 4 5 5 5 4 
    . . . . c c b 4 4 4 b b 4 5 4 4 
    . . . . . . c c c c c c b b 4 . 
    `, SpriteKind.Player)
controller.moveSprite(lemon)
// Prevent the lemon from leaving the screen
lemon.setStayInScreen(true)
info.startCountdown(30)
let statusbar = statusbars.create(20, 4, StatusBarKind.Health)
statusbar.attachToSprite(lemon)
```


## Step Three - Optional Change

If you think that the health bar is too close to the lemon you can go ahead and add some padding to the top.

<hr/>

Do this by clicking the ``||statusbars: +||`` on the ``||statusbars: attach [statusbar] to [lemon]||`` and change ``||statusbars: padding||`` to ``||math: 2||``

```blocks
scene.setBackgroundColor(10)
let lemon = sprites.create(img`
    4 4 4 . . 4 4 4 4 4 . . . . . . 
    4 5 5 4 4 5 5 5 5 5 4 4 . . . . 
    b 4 5 5 1 5 1 1 1 5 5 5 4 . . . 
    . b 5 5 5 5 1 1 5 5 1 1 5 4 . . 
    . b d 5 5 5 5 5 5 5 5 1 1 5 4 . 
    b 4 5 5 5 5 5 5 5 5 5 5 1 5 4 . 
    c d 5 5 5 5 5 5 5 5 5 5 5 5 5 4 
    c d 4 5 5 5 5 5 5 5 5 5 5 1 5 4 
    c 4 5 5 5 d 5 5 5 5 5 5 5 5 5 4 
    c 4 d 5 4 5 d 5 5 5 5 5 5 5 5 4 
    . c 4 5 5 5 5 d d d 5 5 5 5 5 b 
    . c 4 d 5 4 5 d 4 4 d 5 5 5 4 c 
    . . c 4 4 d 4 4 4 4 4 d d 5 d c 
    . . . c 4 4 4 4 4 4 4 4 5 5 5 4 
    . . . . c c b 4 4 4 b b 4 5 4 4 
    . . . . . . c c c c c c b b 4 . 
    `, SpriteKind.Player)
controller.moveSprite(lemon)
// Prevent the lemon from leaving the screen
lemon.setStayInScreen(true)
info.startCountdown(30)
let statusbar = statusbars.create(20, 4, StatusBarKind.Health)
statusbar.attachToSprite(lemon, 2, 0)
```

## Step Four - Label the Health Bar

To give the player some context we will add a label to the bar.

<hr/>

Go back into the ``||statusbars: Status Bar||`` category and grab ``||statusbars: set [statusbar] label ["hp"]||`` placing it at the bottom of our ``||loops: on start||`` container.

<hr/>

>>*Tip HP stands for Hit points*

```blocks
scene.setBackgroundColor(10)
let lemon = sprites.create(img`
    4 4 4 . . 4 4 4 4 4 . . . . . . 
    4 5 5 4 4 5 5 5 5 5 4 4 . . . . 
    b 4 5 5 1 5 1 1 1 5 5 5 4 . . . 
    . b 5 5 5 5 1 1 5 5 1 1 5 4 . . 
    . b d 5 5 5 5 5 5 5 5 1 1 5 4 . 
    b 4 5 5 5 5 5 5 5 5 5 5 1 5 4 . 
    c d 5 5 5 5 5 5 5 5 5 5 5 5 5 4 
    c d 4 5 5 5 5 5 5 5 5 5 5 1 5 4 
    c 4 5 5 5 d 5 5 5 5 5 5 5 5 5 4 
    c 4 d 5 4 5 d 5 5 5 5 5 5 5 5 4 
    . c 4 5 5 5 5 d d d 5 5 5 5 5 b 
    . c 4 d 5 4 5 d 4 4 d 5 5 5 4 c 
    . . c 4 4 d 4 4 4 4 4 d d 5 d c 
    . . . c 4 4 4 4 4 4 4 4 5 5 5 4 
    . . . . c c b 4 4 4 b b 4 5 4 4 
    . . . . . . c c c c c c b b 4 . 
    `, SpriteKind.Player)
controller.moveSprite(lemon)
// Prevent the lemon from leaving the screen
lemon.setStayInScreen(true)
info.startCountdown(30)
let statusbar = statusbars.create(20, 4, StatusBarKind.Health)
statusbar.attachToSprite(lemon, 2, 0)
statusbar.setLabel("HP")
```

## Step Five - Reduce Health on Hit
When we play the game we have a nice health bar now but we have a problem.

The HP doesn't go down when we are hit!

<hr/>

Go down to the ``||sprites: on sprite overlap||`` container and remove the ``||Info: Change score by [1]||`` block

Go back to the ``||statusbars: Status Bars||`` tab and drag the ``||statusbars: change [statusbar] [value] by [0]||``

Change ``||math: 0||`` to ``||math: -1||``

```blocks
let statusbar: StatusBarSprite = null
sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {
    sprite.startEffect(effects.spray, 200)
    statusbar.value += -1
})
```

## Step Six - Lose game on 0 HP
When the lemon runs out of HP we should lose the game!

<hr/>

Go down to the ``||statusbars: Status Bars||`` tab and drag the ``||statusbars: on status bar kind [Health] zero [status]||`` container out.

Drag ``||game: game over [Lose]||`` from the ``||game: Game||`` tab into the ``||statusbars: on status bar kind [Health] zero [status]||`` container.

```blocks
statusbars.onZero(StatusBarKind.Health, function (status) {
    game.over(false)
})
```

## Step Seven - Win Condition
Lets add a way for our player to win the game!

<hr/>

Go down to the ``||info: Info||`` tab and drag the ``||info: on countdown end||`` container out

Drag ``||game: game over [Lose]||`` from the ``||game: Game||`` tab into the ``||info: on countdown end||`` container.

Switch ``||game: game over [Lose]||`` to ``||game: game over [Win]||``

```blocks
info.onCountdownEnd(function () {
    game.over(true)
})
```

## Finish

Congrats on completing this!

You can improve this by doing the following:
- Remove the countdown and add increasing score the longer you are alive
- Slow the player down the longer they are alive
- Add health packs which fly out

```template
sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {
    sprite.startEffect(effects.spray, 200)
    // Increment the score every time your player overlaps with projectile
    info.changeScoreBy(1)
})
let projectile: Sprite = null
scene.setBackgroundColor(10)
let lemon = sprites.create(img`
    4 4 4 . . 4 4 4 4 4 . . . . . . 
    4 5 5 4 4 5 5 5 5 5 4 4 . . . . 
    b 4 5 5 1 5 1 1 1 5 5 5 4 . . . 
    . b 5 5 5 5 1 1 5 5 1 1 5 4 . . 
    . b d 5 5 5 5 5 5 5 5 1 1 5 4 . 
    b 4 5 5 5 5 5 5 5 5 5 5 1 5 4 . 
    c d 5 5 5 5 5 5 5 5 5 5 5 5 5 4 
    c d 4 5 5 5 5 5 5 5 5 5 5 1 5 4 
    c 4 5 5 5 d 5 5 5 5 5 5 5 5 5 4 
    c 4 d 5 4 5 d 5 5 5 5 5 5 5 5 4 
    . c 4 5 5 5 5 d d d 5 5 5 5 5 b 
    . c 4 d 5 4 5 d 4 4 d 5 5 5 4 c 
    . . c 4 4 d 4 4 4 4 4 d d 5 d c 
    . . . c 4 4 4 4 4 4 4 4 5 5 5 4 
    . . . . c c b 4 4 4 b b 4 5 4 4 
    . . . . . . c c c c c c b b 4 . 
    `, SpriteKind.Player)
controller.moveSprite(lemon)
// Prevent the lemon from leaving the screen
lemon.setStayInScreen(true)
info.startCountdown(30)
game.onUpdateInterval(1000, function () {
    // Create a strawberry projectile every second!
    projectile = sprites.createProjectileFromSide(img`
        . . . . . . . 6 . . . . . . . . 
        . . . . . . 8 6 6 . . . 6 8 . . 
        . . . e e e 8 8 6 6 . 6 7 8 . . 
        . . e 2 2 2 2 e 8 6 6 7 6 . . . 
        . e 2 2 4 4 2 7 7 7 7 7 8 6 . . 
        . e 2 4 4 2 6 7 7 7 6 7 6 8 8 . 
        e 2 4 5 2 2 6 7 7 6 2 7 7 6 . . 
        e 2 4 4 2 2 6 7 6 2 2 6 7 7 6 . 
        e 2 4 2 2 2 6 6 2 2 2 e 7 7 6 . 
        e 2 4 2 2 4 2 2 2 4 2 2 e 7 6 . 
        e 2 4 2 2 2 2 2 2 2 2 2 e c 6 . 
        e 2 2 2 2 2 2 2 4 e 2 e e c . . 
        e e 2 e 2 2 4 2 2 e e e c . . . 
        e e e e 2 e 2 2 e e e c . . . . 
        e e e 2 e e c e c c c . . . . . 
        . c c c c c c c . . . . . . . . 
        `, randint(-50, 50), randint(-50, 50))
})
```
