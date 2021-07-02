 ### @explicitHints true
 
# tutorial

## Step 1
1. Open the ``||sprites.Sprites||`` drawer, drag the  ``||variables.set mySprite||`` block into the ``||Loops:on start||``  block. 
2. Click on the grey color oval, select **Gallery** view. Scroll to find the image of a dinosaur, select it and hit "OK". 
3. Rename the character from **mySprite** to **dino**
4. Open the ``||controller.Controller||`` drawer, drag the ``||controller.move mySprite with buttons ||`` into the ``||Loops:on start||``. 
5. Click on the **+** sign on ``||controller.move mySprite with buttons ||`` , change the value of **vx** from 100 to **50**, and **vy** from 100 to **0**.

### ~ tutorialhint
```blocks
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
```
```ghost
mySrite.X = 0
let projectile: Sprite = null
projectile.lifespan = 3000

```

## Step 2
** Step 2**
1. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.set background color ||`` block into the ``||Loops:on start||``  block. Choose a color of your choice.
2. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.set tile map to ||`` into the ``||Loops:on start||`` . 
3. Click on the Grey color square.
4. At the bottom left of the window, set the Image Width from 10 to **32**
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-1/master/assets/tilemap.gif)

### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap()    
```

## Step 3
** Step 3**
1. Draw the ground using **brown** color tile.
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-1/master/assets/Screenshot_2.png)


### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . e e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . e e e e . . e e e . . . . 
        e e e e e . . e e . . . . . . . e e e e e e e . . e e e . . e e 
        `)    
```


## Step 4
** Step 4**
1. Add another layer of grass using the **green** tile.
2. Add **red** tile to represent the water where your Dino will be drown if it falls on these tiles.
3. Add **purple** tile at the end to represent the flag (goal of the game).
4. Add **light blue** tile on top to set the starting point of the game.
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-1/master/assets/Screenshot_4.png)

### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
        . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `)    
```

## Step 5
** Step 5**
1. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.set tile to with wall||`` block into the ``||Loops:on start||``  block.
2. Click on the first grey color oval, choose brown color.
3. Click on the second grey color oval, choose an image from the gallery to be the ground for your game.
4. Toggle the wall **OFF** button to **ON**
5. Repeat Step 1 - 4 above for grass (green), water (red), and flag (purple)
6. For the flag, you can draw it out using the editor.
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-1/master/assets/Screenshot_6.png)

### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
        . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale.Sixteen)    
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
```

## Step 6
** Step 6**
1. Repeat the same step for light blue color tile. But this time, leave the second oval empty.
2. And leave the wall **OFF**

### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
        . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale.Sixteen)    
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
```        

## Step 7
** Step 7**
1. Open the ``||sprites.Sprites||`` drawer, drag the  ``||sprites.set mySprite X to||`` block into the ``||Loops:on start||``  block.
2. To mimick gravity, click on the **x** drop down menu, change **x** to **ay(acceleration y)**
3. Change the value from **0** to **290**

### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
        . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale.Sixteen)    
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
dino.x = 0
<pre><code class="lang-block">let mySprite: Sprite = null

mySprite.x = 0</code></pre>
    dino.set(ay,290)
```    

## Step 8
** Step 8**
1. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.place mySprite on top of random ||`` block into the ``||Loops:on start||``  block.
2. Click on the grey oval, select light blue color
3. Make sure the sprite is **dino**

### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
        . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale.Sixteen)    
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
    dino.ay = 290    
    scene.placeOnRandomTile(dino, 9)
``` 
## Step 9
** Step 9**
1. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.camera follow sprite ||`` block into the ``||Loops:on start||``  block.
2. Make sure the sprite is **dino**


### ~ tutorialhint
```blocks
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
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
        . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale.Sixteen)    
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
    dino.ay = 290    
    scene.placeOnRandomTile(dino, 9)
    scene.cameraFollowSprite(dino)
``` 

## Step 10
** Step 10**
1. Open the ``||controller.Controller||`` drawer, drag the  ``||controller.on A button pressed ||`` onto an empty area.
2. Open the ``||sprites.Sprites||`` drawer, drag the  ``||sprites.set mySprite X to||`` block into the ``||controller.on A button pressed ||``  block.
3. To mimick jumping, click on the **x** drop down menu, change **x** to **vy (velocity y))** 
4. Change the value from **0** to **-140**


### ~ tutorialhint
```blocks

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
        dino.vy = -140
})

```



## Step 11
** Step 11**
1. Open the ``||logic.Logic||`` drawer, drag the  ``||logic.if true then ||`` block into the ``||controller.on A button pressed ||``  block.
2. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.is sprite hitting wall left ||`` block onto the ``||logic:true||``  block.
3. Change **mySprite** to **dino**
4. Change **left** to **bottom**

### ~ tutorialhint
```blocks

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (dino.isHittingTile(CollisionDirection.Bottom)) {
        dino.vy = -140
    }
})

```

## Step 12
** Step 12**
1. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.on sprite of kind Player hits wall ||`` block onto an empty area.
2. Click the grey color oval, select **purple**
3. Open the ``||game.Game||`` drawer, drag the  ``||game.game over ||`` block into the  ``||scene.on sprite of kind Player hits wall ||`` block.
4. Toggle the button from **LOSE** to **WIN**.

### ~ tutorialhint
```blocks

scene.onHitTile(SpriteKind.Player, 10, function (sprite) {
    game.over(true)
})

```


## Step 13
** Step 13**
1. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.on sprite of kind Player hits wall ||`` block onto an empty area.
2. Click the grey color oval, select **red**
3. Open the ``||game.Game||`` drawer, drag the  ``||game.game over ||`` block into the  ``||scene.on sprite of kind Player hits wall ||`` block.

### ~ tutorialhint
```blocks

scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    game.over(false)
})

```


## Step 14
** Step 14**
1. Open the ``||controller.Controller||`` drawer, drag the  ``||controller.on A button pressed ||`` onto an empty area.
2. Change the button **A** to **left**
3. Open the ``||sprites.Sprites||`` drawer, drag the  ``||sprites.set mySprite image to||`` block into the ``||controller.on left button pressed ||``  block.
4. Click on the grey oval, select the dinosaur image looking at left.

### ~ tutorialhint
```blocks

controller.left.onEvent(ControllerButtonEvent.Pressed, function () {
    dino.setImage(img`
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
})

```



## Step 15
** Step 15**
1. Open the ``||controller.Controller||`` drawer, drag the  ``||controller.on A button pressed ||`` onto an empty area.
2. Change the button **A** to **right**
3. Open the ``||sprites.Sprites||`` drawer, drag the  ``||sprites.set mySprite image to||`` block into the ``||controller.on right button pressed ||``  block.
4. Click on the grey oval, select the dinosaur image looking at right.


### ~ tutorialhint
```blocks

controller.right.onEvent(ControllerButtonEvent.Pressed, function () {
    dino.setImage(img`
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
})

```


## Step 16
** Step 16**
Congratulations! You have completed today's tutorial. 
Test out your game. If it does not work, cross check your code with the one in the tutorial hint.

### ~ tutorialhint
```blocks
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
    dino.ay = 290
    controller.moveSprite(dino, 50, 0)

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
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
        . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale.Sixteen)
    scene.placeOnRandomTile(dino, 9)
    scene.cameraFollowSprite(dino)

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (dino.isHittingTile(CollisionDirection.Bottom)) {
        dino.vy = -140
    }
})
controller.left.onEvent(ControllerButtonEvent.Pressed, function () {
    dino.setImage(img`
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
})
scene.onHitTile(SpriteKind.Player, 10, function (sprite) {
    game.over(true)
})
controller.right.onEvent(ControllerButtonEvent.Pressed, function () {
    dino.setImage(img`
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
})

scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    game.over(false)
})

```
