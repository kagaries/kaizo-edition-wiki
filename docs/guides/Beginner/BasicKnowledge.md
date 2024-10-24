<head>
<meta property="og:title" content="MCPReborn Wiki" />
<meta content="A resource to help others get around Minecraft's code." property="og:description" />
<meta property="og:type" content="website" />
<meta content="#43B581" data-react-helmet="true" name="theme-color" />
<meta property="og:url" content="https://archerv123456.github.io/MCPRWiki/" />
</head>

# Basic Knowledge

Minecraft: Java Edition is built on Java, crazy I know, but has many systems that you should be aware of before going further.

## Registries

Minecraft uses a **Registry** System for things like mobs, blocks, items, mob effects, etc.

When you register something, it usually has an **ID** at the start, these IDs **cannot** be the same name as another in the same registry, **cannot** include special characters (besides _), and **cannot** include uppercase keys.

The extra info in the Registry is determined by the type of Registry it is (i.e. MobEffects have uuids and a new mob effect, mobs have a entity type builder, etc).

## Organization

Minecraft is organized fairly well all things considered.

If you want to find things that typically spawn or interact with the world, you can find it in the World folder.

It's recommended you keep things organized the way they are, it works, and trying to change it will cause more pain then needed.

## NBT

NBT (or what's usually CompoundTag) is how the game stores data for items, mobs, and most things that needs data saved.