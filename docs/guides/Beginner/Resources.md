# Resources

Minecraft uses a "resources" folder for stuff like data and assets.

If you remember from Getting Started where the MobEffect you created didn't have a tranlatable (a string that determines what text says), or an icon, this is why.

## Adding Resources

Adding resources is a fairly easy task. First, create a **resources** folder within the **main** folder. This is where the resources will be indexed and used from, as well as compile with as well.

You'll need **ALL** of the base Minecraft assets within the folder as well, which you can get from [**here**](https://mcasset.cloud/1.20.2/).

From here you can start adding everything you need!

### Adding a Translatable

When you see something like ```effect.minecraft.name```, it means that string **doesn't** have a translatable within it's lang file.

**Lang files** are files when have translations for any kind of text specified to have one.

To add something to one, go to ```resources/assets/minecraft/lang``` Here you will find every lang file within minecraft. Now find the lang file that corresponds with your selected language (i.e. US is en_us.json).

Here we can start adding translations.

For example, you can add:

```
"effect.minecraft.name": "name",
```

to give your effect a name!

### Adding an Icon

For adding an icon, you will need an image to use for said icon. It **MUST** be a .png, or Minecraft will not recongize the file.

To get to the MobEffect icons, go to ```resources/assets/minecraft/textures/mob_effect``` This is where you will add the icon to.

Now drag you icon (or copy it) into the folder and name it the same as the ID you chose for the effect. If all goes well the effect should now have an icon rather then the placeholder black and purple square.