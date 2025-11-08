=== fpack Folder, through custom commands only === 
equipment: enables pairing for items and custom textures and models. pairs the texture for the armor when worn. the armor's item texture is in models/item
lang: used for giving names to banner layers, as seen on a banner's tooltip
models/item: pairs filename to texture yes, pairs a custom texture to its model
textures/...: textures for pairing.

=== minecraft Folder, across the server === 
items: enables pairing for items and custom textures through commands. yes, assigns a specific (custom) model based on certain properties of the item. right now we use the numeric range dispatch
lang: across the server, overwrites vanilla name with custom name yes
models/item: across the server, overwrites vanilla texture with custom texture overwrites the model, not necessarily the texture. this isn't always required but best practice is to add a model and a texture
sounds/item/goat_horn: across the server, overwrites vanilla sound with custom sound yes
textures/...: textures for pairing. yes, if named the same as a vanilla item/block, will override that item/block