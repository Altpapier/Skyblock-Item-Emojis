# Skyblock-Item-Emojis
 **A database containing every skyblock item as a Discord emoji. 
 Can only be used in webhooks or slash commands!**
## How do I get the emojis?
In the `emojis.json` file there are all emojis by their skyblock id. As pets and runes all have the same skyblock id (PET, RUNE) those work in a different way. You then have the option to get all the information about the emoji (id *String*, name *String*, formatted *String*, animated *Boolean*)

*If you actually use this, it would be nice if you could give some credit as this took a lot of time making*

*Example*: (Item ID: *HYPERION*)

    "HYPERION": {
	    "id": "902516371882127370",
	    "name": "item_1947",
	    "formatted": "<a:item_1947:902516371882127370>",
	    "animated": true
	}

**Normal Items**:
Get normal items by their item id found in the ExtraAttributes of the item (item -> tag -> ExtraAttributes -> id)

*Example*:

    ExtraAttributes: {
        id: "GRAPPLING_HOOK"
    }
   = `GRAPPLING_HOOK`

**Pets**:
Get pets by their pet type found in the ExtraAttributes of the pet (pet -> tag -> ExtraAttributes -> petInfo  -> type)

*Example*:

    ExtraAttributes: {
        petInfo: "{\"type\":\"ARMADILLO\",\"active\":false,\"exp\":0.0,\"tier\":\"COMMON\",\"hideInfo\":false,\"candyUsed\":0,\"uuid\":\"a8667fe7-9c16-451b-b651-2a0cf115f992\"}",
        originTag: "PET_MENU",
        id: "PET",
        uuid: "a8667fe7-9c16-451b-b651-2a0cf115f992",
        timestamp: "10/28/21 8:00 AM"
    }
    
   = `ARMADILLO`

**Runes**:
Get runes using the rune id found in the runes object found the ExtraAttributes of the rune. Make sure to add `RUNE_` before the id. (rune -> tag -> ExtraAttributes -> runes)

*Example*:

    ExtraAttributes: {
        runes: {
            BLOOD_2: 1
        },
        id: "RUNE"
    }
  = `RUNE_BLOOD_2`

