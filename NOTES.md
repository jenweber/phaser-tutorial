# Notes

## Images

Images are positioned based on their center by default.

0,0 is top left.

`setOrigin` lets you change the origin for positioning.
`this.add.image(0, 0, 'sky').setOrigin(0, 0)` would set it as top left.

Images follow paint order. Star covers up sky:

```
function create ()
{
    this.add.image(400, 300, 'sky');
    this.add.image(400, 300, 'star');
}
```

## Objects

Can be static or dynamic. Use static for things that never move,
like the ground. Static things are not affected by gravity and
you can't set velocity on it when something collides.

```js
platforms = this.physics.add.staticGroup();
platforms.create(400, 568, "ground").setScale(2).refreshBody();
platforms.create(600, 400, "ground");
```

## Groups

Use groups to control objects as a single unit and detect collisions
with them.

## Sprites

Sprites are objects that have animations

```
player = this.physics.add.sprite(100, 450, 'dude');
player.setBounce(0.2);
player.setCollideWorldBounds(true);
```

Sprites have a body property that you can assign things to, like gravity:

```
player.body.setGravityY(300)
```

## Collision

Collision is so, so nice:

```
this.physics.add.collider(player, platforms);
```
