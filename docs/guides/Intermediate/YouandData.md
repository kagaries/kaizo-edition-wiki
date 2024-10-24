<head>
<meta property="og:title" content="MCPReborn Wiki" />
<meta content="A resource to help others get around Minecraft's code." property="og:description" />
<meta property="og:type" content="website" />
<meta content="#43B581" data-react-helmet="true" name="theme-color" />
<meta property="og:url" content="https://archerv123456.github.io/MCPRWiki/" />
</head>

# Data and You

Welcome to the first Intermediate tutorial, before we start, make sure you have your resources folder set up, if you do not you can go [here](../Beginner/Resources.md) for more info.

## What Data?

Minecraft uses JSON for a lot of things. Advancements, recipes, and world generation are just a few. Minecraft also has a main data folder, this is where the things mentioned before live at. You can find this folder at ``resources/data/minecraft/``.

## Soooo, What *can* I do with this?

From here you can add custom recipes, structures, trims, dimensions, advancements and more all from this simple little folder. This is really important for modders who want to add even more to their version.

## Data Generation

To make your and their (Mojang's) life 10x easier, they have data generators to be used, these can be found within ``minecraft/data``.

### Using Data Generation

Within the data folder, you'll find a **Main** class, this is where you start the data generation. If you were to run it with the "all" param, you'll see a new folder be created called 'generated'. Now you might be thinking why we didn't do this in the [Resources](../Beginner/Resources.md) tutorial, that's because if you look in the assets folder you'll notice something. There are files missing, this is why we download them all first (also because it was a beginner tutorial).

What's the point then? It doesn't generate everything we need right? Well, not in terms of the assets, but we get everything for the data part. This is where we learn how to use the **Providers**.

#### Providers

If you'll notice, there are a couple of folders within the data folder, pretty much all include providers and generators. If we give the advancements folder a look, you'll see the **AdvancementProvider**, this is what generates the data, but you'll notice another folder named **packs**, this is the folder where the advancements are defined, there is also the **VanillaAdvancementProvider**. Let's open up the **VanillaStoryAdvancements** class to get an idea on how to use these.

#### Creating Your Own Data

Within the **VanillaStoryAdvancements** class, you'll notice a method named "generate", this is where the advancements are defined. An advancement usually looks like:

```java
AdvancementHolder advancementholder = Advancement.Builder.advancement().display(Blocks.GRASS_BLOCK, Component.translatable("advancements.story.root.title"), Component.translatable("advancements.story.root.description"), new ResourceLocation("textures/gui/advancements/backgrounds/stone.png"), FrameType.TASK, false, false, false).addCriterion("crafting_table", InventoryChangeTrigger.TriggerInstance.hasItems(Blocks.CRAFTING_TABLE)).save(p_248554_, "story/root");
```
When adding your own, you can use the other data around it if you don't know how to add data to that **generator** yet.

## Closing

Data can be fairly simple, but also can be complicated depending on the type of data you're creating/modifying.