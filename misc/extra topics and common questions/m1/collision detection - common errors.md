
# Collision detection - Common errors



## 1. Mixing units

![mixing-units-diagram](./collision%20detection%20-%20mixing%20units%20-%20diagram.png)
![mixing-units-example](./collision%20detection%20-%20mixing%20units%20-%20example.png)


Best option: don't mix different types of units.
- If you use vw/vh like we did in class, use vw/vh for all units (vw for all horizontal units like the width and positionX & vh for all vertical ones).
- If you prefer to use pixels (for example, it can make easier to add images), then use px for all


Alternatives:
- a) convert all to the same units when you do collision detection (ie. if you have the width in px, calculate how much is that in vw, which you can do in js).
- b) if you use px for your images (e.g. the size of the player, size of obstacles, etc), but want your game to use all the available space, you can also get the size of the screen in pixels at the beginning of the game, and do all the calculations based on that.
    - Example:
        - https://github.com/Jimix91/Asteroid-Invader.game/blob/072a981e8c5e22583d5e97dcc53f2c4cbe4e6817/js/main.js#L87
        - (line 87) get the size of the screen in pixels (`clientWidth`, `clientHeight`)
        - (line 96) set the initial position of the player based on the size of the screen
        - (line 126) when the player moves, check if it can move, based on the size of the screen



## 2. Images with transparent background

![transparent-bg](./collision%20detection%20-%20transparent%20bg.png)
