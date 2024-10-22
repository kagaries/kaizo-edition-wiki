# Your First Modification

Welcome to the beginner section on using MCPReborn!

## Setup

To get started go to the **[MCPReborn Github Page](https://github.com/Hexeption/MCP-Reborn)** and download the latest version (1.20.2), and **follow** the instructions on the repo and come back here when you're done.

All done? Good! Now we can start look through Minecraft's source code! To start, search for the **MobEffects** class, here is where we will add something new.

## Mob Effect Creation

In the **MobEffects** class, you should see something like:
<div class="code">
```java
public static final MobEffect MOVEMENT_SPEED = register("speed", (new MobEffect(MobEffectCategory.BENEFICIAL, 3402751)).addAttributeModifier(Attributes.MOVEMENT_SPEED, "91AEAA56-376B-4498-935B-2F7F68070635", (double)0.2F, AttributeModifier.Operation.MULTIPLY_TOTAL));
```
</div>

### Basic Effect

Once there we can starting adding a new effect, to get started type in:

```java
public static final MobEffect NAME = register("name", (new MobEffect(MobEffectCategory.BENEFICIAL, 3402751)));
```

This creates and registers the new effect for us to use! The ```"name"``` is the name id of the effect **MAKE SURE IT NOT SOMETHING THAT ALREADY EXISTS**, It **WILL** make a conflict if you do.

The ```new MobEffect()``` part creates the effect itself, the ```MobEffectCategory``` determines if its on the top row (BENEFICIAL) or bottom row (NEUTRAL/HARMFUL), the ```3402751``` is just the color in decimal.

From there you can start the game, and give yourself the effect! One thing you will notice is the ```effect.minecraft.name``` rather then ```name``` for the effect display name.