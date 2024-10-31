# Food Items

You've made some basic items now (or hopefully have), now we'll learn about how to create food items.

## Creating Basic Food

Creating food is very simple, to start go to the **Foods** class. Here we will define the properties of our food item.

To start off, add something like:

```java
public static final FoodProperties FLINT
```

This is where we will create the properites for the food itself.

Now for the builder, we'll add ``(new FoodProperties.Builder()).build()`` like this:

```java
public static final FoodProperties FLINT = (new FoodProperties.Builder()).build();
```

The properites now exist! But they don't really do anything yet, so lets add some values:

```java
public static final FoodProperties FLINT = (new FoodProperties.Builder()).nutrition(1).saturationMod(0.1f).build();
```

``.nutrition()`` is the amount of hunger bars gain (i.e. 1 is half, 2 is a full one), ``.saturationMod()`` adds to your saturation, this is the bigger one which allows for extremely quick healing, and lasts much longer then normal hunger.

Now we'll need to add this FoodProerties to the item, so navigate to the **Items** class, and we'll add it there.

Once there, find the item you want to add the food properites to, for example:

```java
public static final Item FLINT = registerItem("flint", new Item(new Item.Properties()));
```

Now on the end of the Item.Properites we'll add ``.food(Foods.FLINT)``:

```java
public static final Item FLINT = registerItem("flint", new Item(new Item.Properties().food(Foods.FLINT)));
```

You can now go in-game and eat Flint!

### Effects

Foods also support effect giving like the Golden Apple or Rotten Flesh.

Let's head back over to the **Foods** class, there we'll add an effect to the Flint FoodProperties we just created.

To add the effect, insert ``.effect()`` after the ``.saturationMod()``, then we'll need to add ``new MobEffectInstance()`` within the ``.effect()``:

```java
public static final FoodProperties FLINT = (new FoodProperties.Builder()).nutrition(1).saturationMod(0.1f).effect(new MobEffectInstance()).build();
```

Now in the MobEffectInstance, we'll need to add what effect it will give, the time and amplifer, and if it will be visible or not:

```java
.effect(new MobEffectInstance(MobEffects.POISON, 100, 0))
```

The first value ``MobEffects.POISON`` is the effect it will give on use, the ``100`` is the time it will last for in ticks, and the ``0`` is the amplifier (0 = Base Poison, 1 = Poison 2, etc.). Another thing in a MobEffectInstance is how visible the effect is, for example you can hide both the bubble effects, turn off ambient, and hide the icon by doing:

```java
.effect(new MobEffectInstance(MobEffects.POISON, 100, 0, false, false, false))
```

Now you'll see the ``.effect()`` is still getting mad, this is because you need to add the change for the effect to be applied as well:

```java
.effect(new MobEffectInstance(MobEffects.POISON, 100, 0), 1.0f)
```

The 1.0f is 100% chance, 0.5f would be a 50% chance.

All of it together it should be:

```java
public static final FoodProperties FLINT = (new FoodProperties.Builder()).nutrition(1).saturationMod(0.1f).effect(new MobEffectInstance(MobEffects.POISON, 100, 0), 1.0f).build();
```

## Closing

You now know how to make foods in Minecraft! You can add more then one effect for a food at a time as well, and change the properties of other foods if you want to!