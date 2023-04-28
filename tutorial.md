# Making a Zombie Survival Game!

## Step 1 - Make the Map

Go to the scene catagory and drag the ``||scene:set tilemap to [tilemap]||`` block into the ``||loops:on start||`` event block. Then use the gallery tiles to draw the map!
```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
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
    `, SpriteKind.Player)
scene.cameraFollowSprite(mySprite)
controller.moveSprite(mySprite)
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
	
})
let projectile = sprites.createProjectileFromSprite(img`
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
    `, mySprite, 50, 50)
game.onUpdateInterval(500, function () {
	
})
mySprite.follow(mySprite)
sprites.onOverlap(SpriteKind.Player, SpriteKind.Player, function (sprite, otherSprite) {
	
})
sprites.destroy(mySprite)
info.changeScoreBy(1)
mySprite.setPosition(0, 0)
game.gameOver(true)
```

## Step 2 - Make the Player

Next, go to the sprites catagory and put the ``||sprites:set mySprite to sprite [image] of kind [Player]||`` block below the tilemap block. Now draw the player! After you've drawn the player, go to the scene catagory and drag the ``||scene:camera follow sprite mySprite||`` out and put it beneath the sprite block.

## Step 3 - Make the Controls Part 1

Now, go to the controller catagory and get the ``||controller:move mySprite with buttons||`` event block and put it beneath the other two blocks.

## Step 4 - Make the Controls Part 2

Once again, go to the controller catagory. This time, take out the ``||controller:on [A] button [pressed]||`` event block. Drag it next to the ``||loops:on start||`` event block.

## Step 5 - Make the Controls Part 3

Now, go to the sprites and find the ``||sprites:set projectile to projectile [image] from mySprite with vx [number] vy [number]||`` block. Drag it into the ``||controller:on [A] button [pressed]||`` event block. Now draw the projectile and set the vx to 50 and the vy to 0.

## Step 6 - Test!

Now's your chance to test your game!

## Step 7 - Make the Zombies Part 1

Go to the game catagory and drag the ``||game:on game update every [interval] ms||`` event block out and set the interval (time) to 2000 (two seconds). Put it by the other two event blocks. 

## Step 8 - Make the Zombies Part 2

Go back to the sprites catagory now and get another ``||sprites:set mySprite to sprite [image] of kind [Player]||`` block and put it in the on game update event block. Draw the zombie and change the kind from ``||sprites:[Player]||`` to ``||sprites:[Enemy]||``.
After that, drag the ``||sprites:set myEnemy follow mySprite||`` block out and put it below the zombie sprite block. Click on the ``||variables:myEnemy||`` variable and change it to ``||variables:mySprite2||``. Then click the + and set the follow speed to 50.

## Step 9 - Make the Zombies Part 3

Drag the ``||sprites:set mySprite position to x [number] y [number]||`` block out and put it below the follow block. Then click on the number for x, and move the cursor to the bottom-right, and click. Also, don't forget to set the ``||variables:mySprite||`` to ``||variables:mySprite2||``.

## Step 10 - Test!

Now's another chance to test out your game and see if it works!

## Step 11 - Collisions Part 1

Now it's time to make the player, zombies, and projectiles interact! Go to the sprite catagory and get the ``||sprites:on sprite of kind [Player] overlaps otherSprite of kind [Player]||`` event block. Put it near the other event blocks.

## Step 12 - Collisions Part 2

First, we'll code the projectile/zombie interaction. Set the first ``||sprites:[Player]||`` to ``||sprites:[Projectile]||`` and set the second ``||sprites:[Player]||`` to ``||sprites:[Enemy]||``. Then drag the ``||sprites:destroy mySprite||`` block into the sprite overlap event block. Then drag the red [sprite] from the start of the sprite overlap event and replace the ``||variables:mySprite||`` with it.

## Step 13 - Collisions Part 3

Once you've done that, repeat the process. This time however, replace the ``||variables:mySprite||`` with the red [otherSprite]. After that, go to the info category and drag the ``||info:change score by [number]||`` block, set the number to 1, and put it below the destroy blocks in the overlap event.

## Step 14 - Collisions Part 4

Now it's time to make the zombie/player collsions. Get another ``||sprites:on sprite of kind [Player] overlaps otherSprite of kind [Player]||`` block and set the first ``||sprites:[Player]||`` to ``||sprites:[Enemy]||`` and leave the second ``||sprites:[Player]||`` as it is.

## Step 15 - Collisions Part 5

Now we're going to make it so that if a zombie catches you, the game ends. Go to the game catagory and drag the ``||game:game over [win]||`` block into the zombie/player collision event.

## Tutorial Complete!

Congratulations! You've finished the tutorial!
