# IPSMP_resource_pack
_Resource Pack for the Ice Boat SMP._

> [!IMPORTANT]
> For getting started, first read about resource packs on the [Minecraft Wiki](https://minecraft.wiki/w/Resource_pack).  There is also a [tutorial](https://minecraft.wiki/w/Tutorial:Creating_a_resource_pack) for creating a resource pack and a [tutorial](https://minecraft.wiki/w/Tutorial:Loading_a_resource_pack) for loading it.

> [!NOTE] 
> Note that there are multiple namespaces in this resource pack.  The minecraft namespace is a special in that it will override all vanilla files.  The minecraft namespace folder is also where you will need to pair items to their vanilla item through their <ins>numeric range dispatch</ins>.

## Namespace Folders.

### fpack Folder, through custom commands only
- __./fpack/equipment__: Enables pairing for items and custom textures and models. Pairs the texture for the armor when worn. The armor's item texture is in __./fpack/models/item__.
- __./fpack/lang__: Used for giving names to banner layers, as seen on a banner's tooltip.
- __./fpack/models/item__: Pairs filename to texture; pairs a custom texture to its model.
- __./fpack/textures/...__: Textures for pairing.

### minecraft Folder, across the server
- __./minecraft/items__: Enables pairing for items and custom textures through commands. Assigns a specific (custom) model based on certain properties of the item. Right now we use the <ins>numeric range dispatch</ins>.
- __./minecraft/lang__: Across the server, overrides vanilla name with custom name.
- __./minecraft/models/item__: across the server, overrides vanilla texture with custom model. This isn't always required but best practice is to add a model and a texture.
- __./minecraft/sounds/item/goat_horn__: Across the server, overrides vanilla sound with custom sound.
- __./minecraft/textures/...__: Textures for pairing. If named the same as a vanilla item/block, will override that item/block.

### special effect
If the items need to do something special, then that part needs to go into the [fpack repository](https://github.com/Apogee-Ind/fpack) (not to be confused with the fpack folder)

## Pushing to Live 
Once a change has been made, the repo contents has to be zipped and uploaded. Contact an admin (Frijoles_ is a good contact) for a push to live.

## Testing 
For single player testing, select all contents within the resource pack repo (assets, pack.mcmeta, pack.png, readme.md), right click, and send to compressed folder.  Move the newly created zip to your "resourcepacks" folder, which is found in the installation of your ".minecraft/" folder, see the [tutorial](https://minecraft.wiki/w/Tutorial:Loading_a_resource_pack) for loading it.  This will add the resource pack to all of your single player words, and you can turn the asset on or off in the pause menu: Options/Resource Packs.

### Getting the item
To get the item in game, you will need to use a command block.
```
/give playerNameHere itemName[dataHere] quantity
```
In dataHere, For custom item image, you need to match the itemName to the <ins>numeric range dispatch</ins>, as found in the __./minecraft/items__ folder. 
- minecraft:custom_name: the name of the item.
- minecraft:lore: the tooltip text.
- minecraft:custom_model_data: The custom_model_data will be set to a float, and that float is the <ins>numeric range dispatch</ins>.
- minecraft:equippable: where it will be equippable, and what asset to use.  If you have a wrong custom_model_data, then i

> [!NOTE]
> It is possible to use the replace item command, but you have to finagle with coordinates and is not recommended at this time.

### Examples
If you want to get an item that is normal under the hood but is simply retextured with lore.
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

Example of item that has is equippable.
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

```
/give Rei_Shards minecraft:iron_nugget[
  minecraft:custom_name={"text":"key_1"},
  minecraft:lore=[
    {"color":"dark_aqua","text":"key goes in"},
    {"color":"gray","text":"treasure comes out"}
  ],
  minecraft:custom_model_data={floats:[702]},
] 64
```

For banners follow the tutorial on https://www.planetminecraft.com/blog/make-your-own-banner-patterns-with-a-minecraft-datapack-tutorial/





