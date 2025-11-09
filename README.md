\# IPSMP\_resource\_pack



Resource Pack for the Ice Boat SMP.



\## Folder structure of a Resource Pack



\### fpack Folder, through custom commands only

\- equipment: enables pairing for items and custom textures and models. pairs the texture for the armor when worn. the armor's item texture is in models/item

\- lang: used for giving names to banner layers, as seen on a banner's tooltip

\- models/item: pairs filename to texture yes, pairs a custom texture to its model

\- textures/...: textures for pairing.



\### minecraft Folder, across the server
- items: enables pairing for items and custom textures through commands. yes, assigns a specific (custom) model based on certain properties of the item. right now we use the numeric range dispatch
- lang: across the server, overwrites vanilla name with custom name yes
- models/item: across the server, overwrites vanilla texture with custom texture overwrites the model, not necessarily the texture. this isn't always required but best practice is to add a model and a texture
- sounds/item/goat\_horn: across the server, overwrites vanilla sound with custom sound yes
- textures/...: textures for pairing. yes, if named the same as a vanilla item/block, will override that item/block



\### special effectt

If the items need to do something special, then that part needs to go into the \[fpack respository](https://github.com/Apogee-Ind/fpack) (not to be confused with the fpack folder)





\## Pushing to Live 

Once a change has been made, the repo has to be zipped and uploaded. Contact an admin (Frijoles\_ is a good contact) for a push to live.





\## Testing 

For single player testing, select all contents within the resource pack repo (assets, pack.mcmeta, pack.png, readme.md), right click, and send to compressed folder.  Move the newly created zip to your resourcepacks folder within your ".minecraft" folder.



This will add the resource pack to all of your single player words, and you can turn the asset on or off in the pause menu: Options/Resource Packs...



to get the item in game, you will use a command block.

&nbsp;```

&nbsp;/give playerNameHere itemName\[dataHere] quantity

&nbsp;```



in dataHere, you need to match the itemName to the item number as found in the minecraft/item folder.



Then you have to use a give command. Example of item that has is equipable



```

/give Rei\_Shards minecraft:amethyst\_shard\[minecraft:custom\_name={"text":"Amethyst Crown"},minecraft:lore=\[{"color":"dark\_aqua","text":"line1"},{"color":"gray","text":"line2"}],minecraft:custom\_model\_data={floats:\[115]},minecraft:equippable={slot:head,swappable:false,asset\_id:"fpack:amethyst"}] 64

```



If you want to get an item that is normal and just retextured with lore.


```

/give Rei\_Shards minecraft:iron\_nugget\[minecraft:custom\_name={"text":"key\_1"},minecraft:lore=\[{"color":"dark\_aqua","text":"first line of text"},{"color":"gray","text":"second line of text"}],minecraft:custom\_model\_data={floats:\[121]},asset\_id:"fpack:key\_1"}] 64

```



For banners follow the tutorial on https://www.planetminecraft.com/blog/make-your-own-banner-patterns-with-a-minecraft-datapack-tutorial/





