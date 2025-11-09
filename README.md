# IPSMP_resource_pack
_Resource Pack for the Ice Boat SMP._

> [!IMPORTANT]
> For getting started, first read about resoruce packs on the [Minecraft Wiki](https://minecraft.wiki/w/Resource_pack).  

> [!NOTE] 
> Note that there are multiple namespaces in this resource pack.  The minecraft namespace is a special in that it will override all vanilla files.  The minecraft namespace folder is also where you will need to pair items to their vanilla item through their numeric range dispatch.

## Namespace Folders.

### fpack Folder, through custom commands only
- $${\color{red}{./fpack/equipment}}: Enables pairing for items and custom textures and models. Pairs the texture for the armor when worn. The armor's item texture is in $${\color{red}{./fpack/models/item}}.
- $${\color{red}{./fpack/lang}}: Used for giving names to banner layers, as seen on a banner's tooltip.
- $${\color{red}{./fpack/models/item}}: Pairs filename to texture; pairs a custom texture to its model.
- $${\color{red}{./fpack/textures/...}}: Textures for pairing.

### minecraft Folder, across the server
- $${\color{red}{./minecraft/items}}: Enables pairing for items and custom textures through commands. Assigns a specific (custom) model based on certain properties of the item. Right now we use the __numeric range dispatch__.
- $${\color{red}{./minecraft/lang}}: Across the server, overrides vanilla name with custom name.
- $${\color{red}{./minecraft/models/item}}: across the server, overrides vanilla texture with custom model. This isn't always required but best practice is to add a model and a texture.
- $${\color{red}{./minecraft/sounds/item/goat_horn}}: Across the server, overrides vanilla sound with custom sound.
- $${\color{red}{./minecraft/textures/...}}: tTextures for pairing. If named the same as a vanilla item/block, will override that item/block.

### special effect
If the items need to do something special, then that part needs to go into the [fpack repository](https://github.com/Apogee-Ind/fpack) (not to be confused with the fpack folder)

## Pushing to Live 
Once a change has been made, the repo contents has to be zipped and uploaded. Contact an admin (Frijoles_ is a good contact) for a push to live.

## Testing 
For single player testing, select all contents within the resource pack repo (assets, pack.mcmeta, pack.png, readme.md), right click, and send to compressed folder.  Move the newly created zip to your "./resourcepacks" folder within your ".minecraft" folder.  This will add the resource pack to all of your single player words, and you can turn the asset on or off in the pause menu: Options/Resource Packs.

### Getting the item
To get the item in game, you will need to use a command block.
```
/give playerNameHere itemName[dataHere] quantity
```
In dataHere, you need to match the itemName to the item number, aka __numeric range dispatch__, as found in the $${\color{red}{./minecraft/items}} folder.

> [!NOTE]
> It is possible to use the replace item command, but you have to finagle with coordinates and is not recommended at this time.

### Examples
Then you have to use a give command. Example of item that has is equipable.
```
/give Rei_Shards minecraft:amethyst_shard[
  minecraft:custom_name={"text":"Amethyst Crown"},
  minecraft:lore=[
    {"color":"dark_aqua","text":"first line of text"},
    {"color":"gray","text":"second line of text"}
  ],
  minecraft:custom_model_data={floats:[115]},
  minecraft:equippable={
    slot:head,
    swappable:false,
    asset_id:"fpack:amethyst"
  }
] 64
```

If you want to get an item that is normal under the hood and just retextured with lore.
```
/give Rei_Shards minecraft:iron_nugget[
  minecraft:custom_name={"text":"key_1"},
  minecraft:lore=[
    {"color":"dark_aqua","text":"first line of text"},
    {"color":"gray","text":"second line of text"}
  ],
  minecraft:custom_model_data={floats:[121]},
] 64
```

For banners follow the tutorial on https://www.planetminecraft.com/blog/make-your-own-banner-patterns-with-a-minecraft-datapack-tutorial/





