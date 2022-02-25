# Skyblock-Item-Emojis

**A database containing every skyblock item as a Discord emoji.
Can be used in webhooks or slash commands!**

# Version 2

## Whats new?

- Added the enchantment glint to some items

- Added potions

## How do I get the emojis?

In the `emojisV2.json` file there are all emojis by their skyblock id. You can also choose between `normal` and `enchanted` emojis. Both keys will be provided on every skyblock id but only items that can be enchanted (armor, swords, pickaxes, ...) or have the enchantment glint applied without being enchanted actually have a enchanted version of the emoji. We provide both keys to make it easier for you to implement the emojis into your project. Pets, runes and potions work in a different way.

You can get a link to an emoji by adding the discord emoji Id to the end of this URL: https://cdn.discordapp.com/emojis/EMOJI_ID

_Example: (Item ID: `ROGUE_SWORD`)_

```
"ROGUE_SWORD": {
	"normal": {
		"name": "Rogue_Sword",
		"id": "945325276085252156",
		"formatted": "<:Rogue_Sword:945325276085252156>",
		"animated": false
	},
	"enchanted": {
		"name": "E_Rogue_Sword",
		"id": "945816883838451723",
		"formatted": "<a:E_Rogue_Sword:945816883838451723>",
		"animated": true,
		"enchanted": true
	}
}
```

**Normal Items**:

Get normal items by their item id found in the `ExtraAttributes` of the item (`item` -> `tag` -> `ExtraAttributes` -> `id`)

```
ExtraAttributes: {
	id: "ROGUE_SWORD"
}
```

= `ROGUE_SWORD`

**Pets**:

Get pets by their pet type found in the ExtraAttributes of the pet (`pet` -> `tag` -> `ExtraAttributes` -> `petInfo` -> `type`). After getting the pet type make sure to append `_PET`. If the pet includes a pet skin (`petInfo` -> `skin`) you can just use the id provided there like normal items.

_Example_:

```
ExtraAttributes: {
	petInfo: "{\"type\":\"ARMADILLO\",\"active\":false,\"exp\":0.0,\"tier\":\"COMMON\",\"hideInfo\":false,\"candyUsed\":0,\"uuid\":\"a8667fe7-9c16-451b-b651-2a0cf115f992\"}",
	originTag: "PET_MENU",
	id: "PET",
	uuid: "a8667fe7-9c16-451b-b651-2a0cf115f992",
	timestamp: "10/28/21 8:00 AM"
}
```

= `ARMADILLO_PET`

**Runes**:

Get runes using the rune id found in the runes object found the ExtraAttributes of the rune. Make sure to append `_RUNE` after the id. (`rune` -> `tag` -> `ExtraAttributes` -> `runes`)

_Example_:

```
ExtraAttributes: {
	runes: {
		BLOOD_2: 1
	},
	id: "RUNE"
}
```

= `BLOOD_2_RUNE`

**Potions**:

To get a potion you first need to get the minecraft vanilla potion id. The potion id is found in the first index of the CustomPotionEffects array (`potion` -> `tag` -> `CustomPotionEffects` -> `0` -> `Id`). Now you will need to the potion type (Whether its a `NORMAL` potion or a `SPLASH` potion). This can be found in the ExtraAttributes of the potion (`potion` -> `tag` -> `ExtraAttributes` -> `splash`). If `splash` is `true` the potion is a splash potion.

_Example_:

```
CustomPotionEffects: [{
	Ambient: 0,
	Duration: 20,
	Id: 18,
	Amplifier: 7
}]

ExtraAttributes: {
	splash: true
}
```

= `POTION_SPLASH_18`

# Version 1

## How do I get the emojis?

In the `emojis.json` file there are all emojis by their skyblock id. As pets and runes all have the same skyblock id (PET, RUNE) those work in a different way. You then have the option to get all the information about the emoji (id _String_, name _String_, formatted _String_, animated _Boolean_)

_If you actually use this, it would be nice if you could give some credit as this took a lot of time making_

_Example_: (Item ID: _HYPERION_)

```
"HYPERION": {
	"id": "902516371882127370",
	"name": "item_1947",
	"formatted": "<a:item_1947:902516371882127370>",
	"animated": true
}
```

**Normal Items**:

Get normal items by their item id found in the ExtraAttributes of the item (item -> tag -> ExtraAttributes -> id)

_Example_:

```
ExtraAttributes: {
	id: "GRAPPLING_HOOK"
}
```

= `GRAPPLING_HOOK`

**Pets**:

Get pets by their pet type found in the ExtraAttributes of the pet (pet -> tag -> ExtraAttributes -> petInfo -> type)

_Example_:

```
ExtraAttributes: {
	petInfo: "{\"type\":\"ARMADILLO\",\"active\":false,\"exp\":0.0,\"tier\":\"COMMON\",\"hideInfo\":false,\"candyUsed\":0,\"uuid\":\"a8667fe7-9c16-451b-b651-2a0cf115f992\"}",
	originTag: "PET_MENU",
	id: "PET",
	uuid: "a8667fe7-9c16-451b-b651-2a0cf115f992",
	timestamp: "10/28/21 8:00 AM"
}
```

= `ARMADILLO_PET`

**Runes**:

Get runes using the rune id found in the runes object found the ExtraAttributes of the rune. Make sure to add `RUNE_` before the id. (rune -> tag -> ExtraAttributes -> runes)

_Example_:

```
ExtraAttributes: {
	runes: {
		BLOOD_2: 1
	},
	id: "RUNE"
}
```

= `RUNE_BLOOD_2`
