### @explicitHints true
 
# tutorial

```package
color-coded-tilemap
animation
TomatoCube Arcade Sprites=github:Jacob-Tate/tomatocube-arcade-sprites#master
```

## Step 1

**Step 1**
1. Open the ``||info.Info||`` drawer, drag the  ``||info.set life to 3||`` into the ``||Loops:on start||`` block

### ~ tutorialhint
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-3/master/assets/Screenshot_7.png)

## Step 2
**Step 2**
1. Inside the ``||scene.on sprite of kind Player hits wall ||`` ``||variables.RED||`` block,  delete the ``||game.game over ||`` block 
2. Open the ``||info.Info||`` drawer, drag the  ``||info.change life by -1||`` into the ``||scene.on sprite of kind Player hits wall ||`` ``||variables.RED||`` block

### ~ tutorialhint
```blocks
scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    info.changeLifeBy(-1)
})

```

## Step 3
**Step 3**
1. Duplicate the ``||scene.place mySprite on top of random blue tile||`` from ``||Functions.create_dino||`` block
2. Move the duplicated ``||scene.place mySprite on top of random blue tile||`` block into the  ``||scene.on sprite of kind Player hits wall ||`` ``||variables.RED||`` block

### ~ tutorialhint
```blocks
scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    info.changeLifeBy(-1)    
    scene.placeOnRandomTile(dino, 9)
})

```


## Step 4
**Step 4**
1. Open the ``||music.Music||`` drawer, drag the  ``||music.play sound ba ding||`` into the same block.
2. Change the **ba ding** to any sound of your choice.

### ~ tutorialhint
```blocks
scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    info.changeLifeBy(-1)    
    scene.placeOnRandomTile(dino, 9)
    music.powerDown.play()
})
```


## Step 5
**Step 5**
1. Open the ``||variables.Variables||``  drawer, click on **Make a Variable...**
2. Key in **level**, then hit **OK**
3. Open the ``||variables.Variables||``  drawer, drag the ``||variables.set level to 0||`` into the ``||Loops:on start||`` block. Make sure the ``||variables.set level to 0||`` block is located before the ``||Functions.call setup_level||`` block
4. Change the value from **0** to **1**

### ~ tutorialhint
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-3/master/assets/Screenshot_1.png)


## Step 6
**Step 6**
1. Open the ``||logic.Logic||``  drawer, drag the ``||logic.if true then ||`` block into the ``||Functions.create_map||`` function. Make sure the ``||logic.if true then ||`` block is surrounding the ``||scene.set tile map to ||`` block
2. Open the ``||logic.Logic||``  drawer, drag the ``||logic.0 = 0 ||`` block onto the ``||logic:true||`` block
3. Open the ``||variables.Variables||``  drawer, drag the ``||variables.level||`` onto the first **0** value
4. Change the value of the second **0** to 1

### ~ tutorialhint
```blocks
let level = 0
function create_map () {
    scene.setBackgroundColor(1)
    scene.setTile(7, img`
        7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 
        6 6 7 6 7 6 7 6 6 d 6 7 7 6 7 7 
        d d 6 7 7 6 7 d d d 7 6 d 6 7 6 
        d d d d d d 6 d d d d d d d 6 d 
        d d d d d d d d d d d d d d d d 
        d 1 1 d 1 d d d d d 1 d d d d d 
        d 1 1 d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d b d d d d d d d 1 d 
        d d d d d d d d d d d d d d d d 
        d d b d d d d d d d d b b d d d 
        d d d d d d d d d d d b b d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d 1 d d d d d d d d 
        d d d d d d d d d d d d d d 1 d 
        `, true)
    scene.setTile(14, img`
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        `, true)
    scene.setTile(13, img`
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e b b b b b b d e 
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e d b b b b b b e 
        `, true)
    scene.setTile(2, img`
        c c c c c c c c c c c c c c c c 
        8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 
        8 8 8 6 6 6 8 8 8 6 6 6 6 8 8 8 
        6 6 8 8 8 6 6 6 6 6 6 8 8 8 8 6 
        6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 
        9 9 6 6 6 6 6 9 9 9 9 6 6 6 9 9 
        6 6 6 6 9 9 9 6 6 6 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        `, true)
    scene.setTile(9, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    scene.setTile(10, img`
        . . . . . . . . . . . . . . . . 
        . . . . . c . . . . . . . . . . 
        . . . . . f 2 2 . . . . . . . . 
        . . . . . f 2 2 2 2 2 . . . . . 
        . . . . . f 2 2 2 2 2 2 2 2 . . 
        . . . . . f 2 2 2 2 2 2 2 . . . 
        . . . . . f 2 2 2 2 . . . . . . 
        . . . . . f 2 . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . f f f . . . . . . . . . 
        . . . f c c c f . . . . . . . . 
        . . f c c c c c f . . . . . . . 
        `, true)
    scene.setTile(5, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    if (level == 1) {     
        scene.setTileMap(img`
            9 9 9 . . . . . . . . . . . . . . . . . . . . . 5 . . . . . . . 
            . . . . . . . . . . . . 5 . 5 . . . . . . . 5 . . . . . . . . . 
            . . . . . . . . . . . 5 . 5 . . . . . 5 . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . . . . . . 7 7 . . . 5 . . . . . 
            . . . 5 . . . . . . d d d d d . . . . . 7 e e . . . . . . . . . 
            . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
            7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
            e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
            `)          
    }
}    
```




## Step 7
**Step 7**
1. Click on the **+** sign in the ``||logic.if true then ||`` block to expose the ``||logic:else||`` block
2. Drag the  ``||scene.set tile map to ||`` into the ``||logic:else||`` block

### ~ tutorialhint
```blocks
let level = 0
function create_map () {
    scene.setBackgroundColor(1)
    scene.setTile(7, img`
        7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 
        6 6 7 6 7 6 7 6 6 d 6 7 7 6 7 7 
        d d 6 7 7 6 7 d d d 7 6 d 6 7 6 
        d d d d d d 6 d d d d d d d 6 d 
        d d d d d d d d d d d d d d d d 
        d 1 1 d 1 d d d d d 1 d d d d d 
        d 1 1 d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d b d d d d d d d 1 d 
        d d d d d d d d d d d d d d d d 
        d d b d d d d d d d d b b d d d 
        d d d d d d d d d d d b b d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d 1 d d d d d d d d 
        d d d d d d d d d d d d d d 1 d 
        `, true)
    scene.setTile(14, img`
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        `, true)
    scene.setTile(13, img`
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e b b b b b b d e 
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e d b b b b b b e 
        `, true)
    scene.setTile(2, img`
        c c c c c c c c c c c c c c c c 
        8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 
        8 8 8 6 6 6 8 8 8 6 6 6 6 8 8 8 
        6 6 8 8 8 6 6 6 6 6 6 8 8 8 8 6 
        6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 
        9 9 6 6 6 6 6 9 9 9 9 6 6 6 9 9 
        6 6 6 6 9 9 9 6 6 6 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        `, true)
    scene.setTile(9, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    scene.setTile(10, img`
        . . . . . . . . . . . . . . . . 
        . . . . . c . . . . . . . . . . 
        . . . . . f 2 2 . . . . . . . . 
        . . . . . f 2 2 2 2 2 . . . . . 
        . . . . . f 2 2 2 2 2 2 2 2 . . 
        . . . . . f 2 2 2 2 2 2 2 . . . 
        . . . . . f 2 2 2 2 . . . . . . 
        . . . . . f 2 . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . f f f . . . . . . . . . 
        . . . f c c c f . . . . . . . . 
        . . f c c c c c f . . . . . . . 
        `, true)
    scene.setTile(5, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    if (level == 1) {     
        scene.setTileMap(img`
            9 9 9 . . . . . . . . . . . . . . . . . . . . . 5 . . . . . . . 
            . . . . . . . . . . . . 5 . 5 . . . . . . . 5 . . . . . . . . . 
            . . . . . . . . . . . 5 . 5 . . . . . 5 . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . . . . . . 7 7 . . . 5 . . . . . 
            . . . 5 . . . . . . d d d d d . . . . . 7 e e . . . . . . . . . 
            . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
            7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
            e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
            `)          
    }
    else{
        scene.setTileMap()        
    }
}    
```

    
## Step 8
**Step 8**   
1. Click on the Grey color square on Tilemap.
2. At the bottom left of the window, change the Image Width from 10 to **32**
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-3/master/assets/Screenshot_3.png)


## Step 9
**Step 9**
Draw out a new map using the below color tiles:
1. **brown** tile for ground
2. **green** tile for grass
3. **yellow** tile for egg
4. **red** tile for ocean/fire
5. **purple** tile for flag
6. **blue** tile for drop off point
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-3/master/assets/Screenshot_2a.png)



## Step 10
**Step 10**
1. Open the ``||logic.Logic||`` drawer, drag the  ``||logic.if true then ... else ...||`` into the ``||scene.on sprite of kind Player hits wall ||``  ``||game.PURPLE ||`` block
2. Open the ``||logic.Logic||`` drawer, drag the ``||logic.0 = 0 ||`` block onto the ``||logic:true||`` block
3. Open the ``||variables.Variables||``  drawer, drag the ``||variables.level||`` onto the first **0** value
4. Change the second **0** value to 2
5. Move the ``||game.game over ||`` (WIN) block into the ``||logic:if||`` block


### ~ tutorialhint
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-3/master/assets/Screenshot_5.png)

## Step 11
**Step 11**
1. Open the ``||variables.Variables||``  drawer, drag the ``||variables.change level by 1||`` into the ``||logic:else||`` block
2. At the category drawer, click on the **Advanced** arrow to expand more category
3. Open the ``||Functions.Functions||`` drawer, drag the ``||Functions.setup_level||`` function block into the ``||logic:else||`` block


### ~ tutorialhint
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-3/master/assets/Screenshot_6.png)

## Step 12
**Step 12**
1. Move the ``||scene.place mySprite on top of random blue tile||`` from ``||Functions.create_dino||`` block into the ``||Functions:setup_level||`` block

### ~ tutorialhint
```blocks
function setup_level () {
    clear_level()
    create_map()
    create_eggs()
    scene.placeOnRandomTile(dino, 9)
}

function create_map(){codes}
function create_eggs(){codes}
function clear_level(){codes}
```
    

## Step 13
**Step 13**
1. Open the ``||game.Game||``  drawer, drag the ``||game.splash ''||`` block into the ``||Functions.setup_level||`` block
2. Make sure the ``||game.splash ''||`` block  is right after the ``||Functions.clear_level||`` block
3. Open the ``||text.Text||``  drawer, drag the ``||text.join "Hello" "World" -+ ''||`` block onto the **..** of ``||game.splash ''||`` block 
4. Change the text "**Hello**" to "**Level **" (note the additional space after Level)
5. Open the ``||variables.Variables||``  drawer, drag the ``||variables.level||`` onto the text **World**


### ~ tutorialhint
```blocks
function setup_level () {
    clear_level()
    game.splash("Level " + level)
    create_map()
    create_eggs()
    scene.placeOnRandomTile(dino, 9)
}

function create_map(){codes}
function create_eggs(){codes}
function clear_level(){codes}
```



## Step 14
**Step 14**
You have successfully created a game with multi-level!

**Quiz:** Can you add another level (level 3) to your game?
(You may refer to the image in the tutorial hint for clue)


### ~ tutorialhint
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-3/master/assets/Screenshot_4.png)


## Step 15
** Step 15**
Congratulations! You have completed today's tutorial. 
Test out your game. If it does not work, cross check your code with the codes in the tutorial hint.

### ~ tutorialhint
```blocks
let anim_stand_left: animation.Animation = null
let anim_stand_right: animation.Animation = null
let egg: Sprite = null
let tile_list: tiles.Tile[] = []
let dino: Sprite = null
let anim_walk_right: animation.Animation = null
let anim_walk_left: animation.Animation = null
let level = 0
level = 1
enum ActionKind {
    walking_right,
    walking_left,
    standing_right,
    standing_left
}
namespace SpriteKind {
    export const background = SpriteKind.create()
}
setup_level()
create_dino()
info.setScore(0)
info.setLife(3)
scene.onHitTile(SpriteKind.Player, 10, function (sprite) {
    if (level == 3) {
        game.over(true)
    } else {
        level += 1
        setup_level()
    }
})
function setup_level () {
    clear_level()
    game.splash("Level " + level)
    create_map()
    create_eggs()
    scene.placeOnRandomTile(dino, 9)
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    info.changeScoreBy(1)
    otherSprite.destroy()
    music.jumpUp.play()
})

function create_map () {
    scene.setBackgroundColor(1)
    scene.setTile(7, img`
        7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 
        6 6 7 6 7 6 7 6 6 d 6 7 7 6 7 7 
        d d 6 7 7 6 7 d d d 7 6 d 6 7 6 
        d d d d d d 6 d d d d d d d 6 d 
        d d d d d d d d d d d d d d d d 
        d 1 1 d 1 d d d d d 1 d d d d d 
        d 1 1 d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d b d d d d d d d 1 d 
        d d d d d d d d d d d d d d d d 
        d d b d d d d d d d d b b d d d 
        d d d d d d d d d d d b b d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d 1 d d d d d d d d 
        d d d d d d d d d d d d d d 1 d 
        `, true)
    scene.setTile(14, img`
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        `, true)
    scene.setTile(2, img`
        c c c c c c c c c c c c c c c c 
        8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 
        8 8 8 6 6 6 8 8 8 6 6 6 6 8 8 8 
        6 6 8 8 8 6 6 6 6 6 6 8 8 8 8 6 
        6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 
        9 9 6 6 6 6 6 9 9 9 9 6 6 6 9 9 
        6 6 6 6 9 9 9 6 6 6 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        `, true)
    scene.setTile(10, img`
        . . . . . . . . . . . . . . . . 
        . . . . . c . . . . . . . . . . 
        . . . . . f 2 2 . . . . . . . . 
        . . . . . f 2 2 2 2 2 . . . . . 
        . . . . . f 2 2 2 2 2 2 2 2 . . 
        . . . . . f 2 2 2 2 2 2 2 . . . 
        . . . . . f 2 2 2 2 . . . . . . 
        . . . . . f 2 . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . f f f . . . . . . . . . 
        . . . f c c c f . . . . . . . . 
        . . f c c c c c f . . . . . . . 
        `, true)
    scene.setTile(9, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    scene.setTile(5, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    if (level == 1) {
        scene.setTileMap(img`
            9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . . . . . . 5 . . . . . . . . . . 
            . . . . . . . . . . . . 5 . . . . . . . . . . . . . . . . . . . 
            . . . . . . . 5 . . . . . . . . . . . . . 7 7 . . . 5 . . . . . 
            . . . 5 . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
            . . . . . . . . . . . . . . . . . 5 . 7 e e e . . 7 7 7 . . . a 
            7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
            e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
            `)
    } else if (level == 2) {
        scene.setTileMap(img`
            9 9 9 . . . . . . . . . 5 . . . . . . . . . . . . . . . . . 5 . 
            . . . . . . . . . . . . . . . . . 5 . . . . . . . . . . . . . . 
            7 7 7 7 . 5 . . . . . . e . . . . . . . . . . . . 5 . e . . e e 
            e e e e . . . . . . . . . . . . . . . . . 7 . . . . . . . . . . 
            . . . . . . . . . . e . . 5 . e . . . . 7 e . . 7 . . . . . . . 
            . 5 . . . . . . e . . . . . . . . . 7 7 e e . . e 7 . . . . . a 
            . 7 7 7 7 7 7 . . . . . 7 7 . . . . e e e e . . e e 7 . . 7 7 7 
            2 e e e e e e 2 2 2 2 2 e e 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 e e e 
            `)
    } else {
        scene.setTileMap(img`
            9 9 9 . . . . . 
            . . . . . . . . 
            7 7 7 7 . 5 . . 
            e e e e . . . . 
            . . . . . . . . 
            . 5 . . . . . . 
            . 7 7 7 7 7 7 . 
            . e e e e e e . 
            . . . . . . . . 
            . . . . . . . 5 
            . . . . . . . . 
            . . . . . . . . 
            . . . e e e e . 
            . . . . . . . . 
            . 5 . . . . . . 
            . . . . . 5 . . 
            . . . . . . . . 
            . . . . . . . . 
            . e . . . . . . 
            . e e e e . . . 
            . . . . . . . . 
            . . 5 . . . . 5 
            . . . . . . . . 
            . . . . . e e e 
            . . . . . . . . 
            e e . . . . . . 
            . e e . . . . . 
            . . . e . . . 5 
            . . . . . . . . 
            . . . . . e . . 
            a . . . . . . e 
            e e e e e 2 2 2 
            `)
    }
}
scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    info.changeLifeBy(-1)
    scene.placeOnRandomTile(dino, 9)
    music.powerDown.play()
})
controller.right.onEvent(ControllerButtonEvent.Released, function () {
    animation.setAction(dino, ActionKind.standing_right)
})
controller.left.onEvent(ControllerButtonEvent.Released, function () {
    animation.setAction(dino, ActionKind.standing_left)
})
controller.right.onEvent(ControllerButtonEvent.Pressed, function () {
    animation.setAction(dino, ActionKind.walking_right)
})
function create_eggs () {
    tile_list = scene.getTilesByType(5)
    for (let value2 of tile_list) {
        egg = sprites.create(img`
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . f f . . . . . . . 
            . . . . . . f 5 5 f . . . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . f 5 1 1 5 f . . . . . 
            . . . . f 5 5 5 1 5 5 f . . . . 
            . . . . f 5 5 5 5 5 5 f . . . . 
            . . . . f 5 5 5 5 5 5 f . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . . f f f f . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Food)
        scene.place(value2, egg)
        animation.runMovementAnimation(
        egg,
        animation.animationPresets(animation.bobbing),
        2000,
        true
        )
    }
}
function create_stand_animation () {
    anim_stand_right = animation.createAnimation(ActionKind.standing_right, 200)
    anim_stand_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . f 4 4 f 7 f 7 7 7 7 7 7 f . . 
        f 7 7 f 7 7 f 7 7 7 7 7 7 f . . 
        . f 7 7 7 7 7 7 d d 7 f . . . . 
        . . f 7 7 7 7 d d d 7 f . . . . 
        . . . f 7 7 7 d d d 7 f . . . . 
        . . . . f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_stand_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
        . . f f 7 7 f 7 7 7 7 7 7 f . . 
        . 4 4 f 7 7 7 7 d d 7 f . . . . 
        4 f f 7 7 7 7 d d d 7 f . . . . 
        f 7 7 7 7 7 7 d d d 7 f . . . . 
        f f f f f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_stand_left = animation.createAnimation(ActionKind.standing_left, 200)
    anim_stand_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 f . 
        . . f 7 7 7 7 7 7 f 7 7 7 7 7 f 
        . . . . f 7 d d 7 7 7 7 7 7 f . 
        . . . . f 7 d d d 7 7 7 7 f . . 
        . . . . f 7 d d d 7 7 7 f . . . 
        . . . . f 7 d f f 7 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_stand_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 . . 
        . . f 7 7 7 7 7 7 f 7 7 f f . . 
        . . . . f 7 d d 7 7 7 7 f 4 4 . 
        . . . . f 7 d d d 7 7 7 7 f f 4 
        . . . . f 7 d d d 7 7 7 7 7 7 f 
        . . . . f 7 d f f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)
    animation.attachAnimation(dino, anim_stand_left)
    animation.attachAnimation(dino, anim_stand_right)
}

function create_walking_animation () {
    anim_walk_left = animation.createAnimation(ActionKind.walking_left, 100)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . . . f 7 7 7 7 7 7 f 4 4 . . 
        . . . . f 7 7 7 7 7 7 7 f f . . 
        . . . . f 7 d d f 7 7 7 f 4 4 . 
        . . . . f 7 d f 7 7 7 7 7 f f 4 
        . . . . f 7 f 7 7 7 f 7 7 7 7 f 
        . . . . f f f 7 7 f f f f f f f 
        . . . . . . . f f f . . . . . . 
        `)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . . . f 7 7 7 7 7 7 f 4 4 . . 
        . . . . f 7 7 7 7 7 7 7 f f . . 
        . . . . f 7 7 f 7 7 7 7 f 4 4 . 
        . . . . f 7 7 f 7 7 7 7 7 f f 4 
        . . . . f 7 7 d f 7 7 7 7 7 7 f 
        . . . . f 7 7 d f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . . . f 7 7 7 7 7 7 f 4 4 . . 
        . . . . f 7 7 7 7 7 7 7 f f . . 
        . . . f f 7 d d d 7 7 7 f 4 4 . 
        . . . f 7 7 d d 7 7 7 7 7 f f 4 
        . . . f 7 7 d d 7 7 7 7 7 7 7 f 
        . . . f f f f f f 7 7 f f f f f 
        . . . . . . . . . f f f . . . . 
        `)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 . . 
        . . f 7 7 7 7 7 7 f 7 7 f f . . 
        . . . . f 7 d d 7 7 7 7 f 4 4 . 
        . . . . f 7 d d d 7 7 7 7 f f 4 
        . . . . f 7 d d d 7 7 7 7 7 7 f 
        . . . . f 7 d f f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)
    anim_walk_right = animation.createAnimation(ActionKind.walking_right, 100)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 7 7 7 7 7 f . . . . 
        . . f f 7 7 7 7 7 7 7 f . . . . 
        . 4 4 f 7 7 7 f d d 7 f . . . . 
        4 f f 7 7 7 7 7 f d 7 f . . . . 
        f 7 7 7 7 f 7 7 7 f 7 f . . . . 
        f f f f f f f 7 7 f f f . . . . 
        . . . . . . f f f f . . . . . . 
        `)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 7 7 7 7 7 f . . . . 
        . . f f 7 7 7 7 7 7 7 f . . . . 
        . 4 4 f 7 7 7 7 f 7 7 f . . . . 
        4 f f 7 7 7 7 7 f 7 7 f . . . . 
        f 7 7 7 7 7 7 f d 7 7 f . . . . 
        f f f f f 7 7 f d 7 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 7 7 7 7 7 f . . . . 
        . . f f 7 7 7 7 7 7 7 f . . . . 
        . 4 4 f 7 7 7 d d d 7 f f . . . 
        4 f f 7 7 7 7 7 d d 7 7 f . . . 
        f 7 7 7 7 7 7 7 d d 7 7 f . . . 
        f f f f f f 7 7 f f f f f . . . 
        . . . . . f f f . . . . . . . . 
        `)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
        . . f f 7 7 f 7 7 7 7 7 7 f . . 
        . 4 4 f 7 7 7 7 d d 7 f . . . . 
        4 f f 7 7 7 7 d d d 7 f . . . . 
        f 7 7 7 7 7 7 d d d 7 f . . . . 
        f f f f f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    animation.attachAnimation(dino, anim_walk_left)
    animation.attachAnimation(dino, anim_walk_right)
}
function create_dino () {
    dino = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
        . . f f 7 7 f 7 7 7 7 7 7 f . . 
        . 4 4 f 7 7 7 7 d d 7 f . . . . 
        4 f f 7 7 7 7 d d d 7 f . . . . 
        f 7 7 7 7 7 7 d d d 7 f . . . . 
        f f f f f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `, SpriteKind.Player)
    controller.moveSprite(dino, 50, 0)
    dino.ay = 290
    scene.cameraFollowSprite(dino)
    create_stand_animation()
    create_walking_animation()
}
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (dino.isHittingTile(CollisionDirection.Bottom)) {
        dino.vy = -140
    }
})
function clear_level () {
    for (let value of sprites.allOfKind(SpriteKind.Food)) {
        value.destroy()
    }
}
controller.left.onEvent(ControllerButtonEvent.Pressed, function () {
    animation.setAction(dino, ActionKind.walking_left)
})
```

```ghost

let projectile: Sprite = null
projectile.lifespan = 3000
    if (projectile.isHittingTile(CollisionDirection.Bottom)) {
        projectile.vy = -135
    }
projectile.setImage(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 . . 
        . . f 7 7 7 7 7 7 f 7 7 f f . . 
        . . . . f 7 d d 7 7 7 7 f 4 4 . 
        . . . . f 7 d d d 7 7 7 7 f f 4 
        . . . . f 7 d d d 7 7 7 7 7 7 f 
        . . . . f 7 d f f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)

scene.placeOnRandomTile(projectile, 9)      
scene.cameraFollowSprite(projectile)

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (projectile.isHittingTile(CollisionDirection.Bottom)) {
        projectile.vy = -140
    }
})  

``` 



```template
enum ActionKind {
    walking_right,
    walking_left
    standing_right,
    standing_left
}
namespace SpriteKind {
    export const background = SpriteKind.create()
}
let anim_stand_left: animation.Animation = null
let anim_stand_right: animation.Animation = null
let egg: Sprite = null
let tile_list: tiles.Tile[] = []
let dino: Sprite = null
let anim_walk_right: animation.Animation = null
let anim_walk_left: animation.Animation = null
function setup_level(){
clear_level()
create_map()
create_eggs()
}
function clear_level(){
    for (let value of sprites.allOfKind(SpriteKind.Food)) {
        value.destroy()
    }
}
function create_map () {
    scene.setBackgroundColor(1)
    scene.setTile(7, img`
        7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 
        6 6 7 6 7 6 7 6 6 d 6 7 7 6 7 7 
        d d 6 7 7 6 7 d d d 7 6 d 6 7 6 
        d d d d d d 6 d d d d d d d 6 d 
        d d d d d d d d d d d d d d d d 
        d 1 1 d 1 d d d d d 1 d d d d d 
        d 1 1 d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d b d d d d d d d 1 d 
        d d d d d d d d d d d d d d d d 
        d d b d d d d d d d d b b d d d 
        d d d d d d d d d d d b b d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d 1 d d d d d d d d 
        d d d d d d d d d d d d d d 1 d 
        `, true)
    scene.setTile(14, img`
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        `, true)
    scene.setTile(2, img`
        c c c c c c c c c c c c c c c c 
        8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 
        8 8 8 6 6 6 8 8 8 6 6 6 6 8 8 8 
        6 6 8 8 8 6 6 6 6 6 6 8 8 8 8 6 
        6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 
        9 9 6 6 6 6 6 9 9 9 9 6 6 6 9 9 
        6 6 6 6 9 9 9 6 6 6 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        `, true)
    scene.setTile(10, img`
        . . . . . . . . . . . . . . . . 
        . . . . . c . . . . . . . . . . 
        . . . . . f 2 2 . . . . . . . . 
        . . . . . f 2 2 2 2 2 . . . . . 
        . . . . . f 2 2 2 2 2 2 2 2 . . 
        . . . . . f 2 2 2 2 2 2 2 . . . 
        . . . . . f 2 2 2 2 . . . . . . 
        . . . . . f 2 . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . f f f . . . . . . . . . 
        . . . f c c c f . . . . . . . . 
        . . f c c c c c f . . . . . . . 
        `, true)
    scene.setTile(9, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    scene.setTile(5, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 5 . . . . . . . . . . 
        . . . . . . . . . . . . 5 . . . . . . . . . . . . . . . . . . . 
        . . . . . . . 5 . . . . . . . . . . . . . 7 7 . . . 5 . . . . . 
        . . . 5 . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . 5 . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `)
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    info.changeScoreBy(1)
    otherSprite.destroy()
    music.jumpUp.play()
})
function create_walking_animation () {
    anim_walk_left = animation.createAnimation(ActionKind.walking_left, 100)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . . . f 7 7 7 7 7 7 f 4 4 . . 
        . . . . f 7 7 7 7 7 7 7 f f . . 
        . . . . f 7 d d f 7 7 7 f 4 4 . 
        . . . . f 7 d f 7 7 7 7 7 f f 4 
        . . . . f 7 f 7 7 7 f 7 7 7 7 f 
        . . . . f f f 7 7 f f f f f f f 
        . . . . . . . f f f . . . . . . 
        `)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . . . f 7 7 7 7 7 7 f 4 4 . . 
        . . . . f 7 7 7 7 7 7 7 f f . . 
        . . . . f 7 7 f 7 7 7 7 f 4 4 . 
        . . . . f 7 7 f 7 7 7 7 7 f f 4 
        . . . . f 7 7 d f 7 7 7 7 7 7 f 
        . . . . f 7 7 d f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . . . f 7 7 7 7 7 7 f 4 4 . . 
        . . . . f 7 7 7 7 7 7 7 f f . . 
        . . . f f 7 d d d 7 7 7 f 4 4 . 
        . . . f 7 7 d d 7 7 7 7 7 f f 4 
        . . . f 7 7 d d 7 7 7 7 7 7 7 f 
        . . . f f f f f f 7 7 f f f f f 
        . . . . . . . . . f f f . . . . 
        `)
    anim_walk_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 . . 
        . . f 7 7 7 7 7 7 f 7 7 f f . . 
        . . . . f 7 d d 7 7 7 7 f 4 4 . 
        . . . . f 7 d d d 7 7 7 7 f f 4 
        . . . . f 7 d d d 7 7 7 7 7 7 f 
        . . . . f 7 d f f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)
    anim_walk_right = animation.createAnimation(ActionKind.walking_right, 100)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 7 7 7 7 7 f . . . . 
        . . f f 7 7 7 7 7 7 7 f . . . . 
        . 4 4 f 7 7 7 f d d 7 f . . . . 
        4 f f 7 7 7 7 7 f d 7 f . . . . 
        f 7 7 7 7 f 7 7 7 f 7 f . . . . 
        f f f f f f f 7 7 f f f . . . . 
        . . . . . . f f f f . . . . . . 
        `)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 7 7 7 7 7 f . . . . 
        . . f f 7 7 7 7 7 7 7 f . . . . 
        . 4 4 f 7 7 7 7 f 7 7 f . . . . 
        4 f f 7 7 7 7 7 f 7 7 f . . . . 
        f 7 7 7 7 7 7 f d 7 7 f . . . . 
        f f f f f 7 7 f d 7 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 7 7 7 7 7 f . . . . 
        . . f f 7 7 7 7 7 7 7 f . . . . 
        . 4 4 f 7 7 7 d d d 7 f f . . . 
        4 f f 7 7 7 7 7 d d 7 7 f . . . 
        f 7 7 7 7 7 7 7 d d 7 7 f . . . 
        f f f f f f 7 7 f f f f f . . . 
        . . . . . f f f . . . . . . . . 
        `)
    anim_walk_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
        . . f f 7 7 f 7 7 7 7 7 7 f . . 
        . 4 4 f 7 7 7 7 d d 7 f . . . . 
        4 f f 7 7 7 7 d d d 7 f . . . . 
        f 7 7 7 7 7 7 d d d 7 f . . . . 
        f f f f f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    animation.attachAnimation(dino, anim_walk_left)
    animation.attachAnimation(dino, anim_walk_right)
}

function create_dino () {
    dino = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
        . . f f 7 7 f 7 7 7 7 7 7 f . . 
        . 4 4 f 7 7 7 7 d d 7 f . . . . 
        4 f f 7 7 7 7 d d d 7 f . . . . 
        f 7 7 7 7 7 7 d d d 7 f . . . . 
        f f f f f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `, SpriteKind.Player)
    controller.moveSprite(dino, 50, 0)
    dino.ay = 290
    scene.cameraFollowSprite(dino)
    scene.placeOnRandomTile(dino, 9)
    create_stand_animation()
    create_walking_animation()
}
scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    game.over(false)
})
scene.onHitTile(SpriteKind.Player, 10, function (sprite) {
    game.over(true)
})

function create_stand_animation () {
    anim_stand_right = animation.createAnimation(ActionKind.standing_right, 200)
    anim_stand_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . f 4 4 f 7 f 7 7 7 7 7 7 f . . 
        f 7 7 f 7 7 f 7 7 7 7 7 7 f . . 
        . f 7 7 7 7 7 7 d d 7 f . . . . 
        . . f 7 7 7 7 d d d 7 f . . . . 
        . . . f 7 7 7 d d d 7 f . . . . 
        . . . . f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_stand_right.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
        . . f f 7 7 f 7 7 7 7 7 7 f . . 
        . 4 4 f 7 7 7 7 d d 7 f . . . . 
        4 f f 7 7 7 7 d d d 7 f . . . . 
        f 7 7 7 7 7 7 d d d 7 f . . . . 
        f f f f f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_stand_left = animation.createAnimation(ActionKind.standing_left, 200)
    anim_stand_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 f . 
        . . f 7 7 7 7 7 7 f 7 7 7 7 7 f 
        . . . . f 7 d d 7 7 7 7 7 7 f . 
        . . . . f 7 d d d 7 7 7 7 f . . 
        . . . . f 7 d d d 7 7 7 f . . . 
        . . . . f 7 d f f 7 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `)
    anim_stand_left.addAnimationFrame(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 . . 
        . . f 7 7 7 7 7 7 f 7 7 f f . . 
        . . . . f 7 d d 7 7 7 7 f 4 4 . 
        . . . . f 7 d d d 7 7 7 7 f f 4 
        . . . . f 7 d d d 7 7 7 7 7 7 f 
        . . . . f 7 d f f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)
    animation.attachAnimation(dino, anim_stand_left)
    animation.attachAnimation(dino, anim_stand_right)
}
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (dino.isHittingTile(CollisionDirection.Bottom)) {
        dino.vy = -140
    }
})
controller.left.onEvent(ControllerButtonEvent.Pressed, function () {
    animation.setAction(dino, ActionKind.walking_left)
})
controller.right.onEvent(ControllerButtonEvent.Released, function () {
    animation.setAction(dino, ActionKind.standing_right)
})
controller.left.onEvent(ControllerButtonEvent.Released, function () {
    animation.setAction(dino, ActionKind.standing_left)
})
controller.right.onEvent(ControllerButtonEvent.Pressed, function () {
    animation.setAction(dino, ActionKind.walking_right)
})
function create_eggs () {
    tile_list = scene.getTilesByType(5)
    for (let value of tile_list) {
        egg = sprites.create(img`
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . f f . . . . . . . 
            . . . . . . f 5 5 f . . . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . f 5 1 1 5 f . . . . . 
            . . . . f 5 5 5 1 5 5 f . . . . 
            . . . . f 5 5 5 5 5 5 f . . . . 
            . . . . f 5 5 5 5 5 5 f . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . . f f f f . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Food)
        scene.place(value, egg)
        animation.runMovementAnimation(
        egg,
        animation.animationPresets(animation.bobbing),
        2000,
        true
        )
    }
}
setup_level()
create_dino()
info.setScore(0)

```

