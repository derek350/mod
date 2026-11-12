# Steel (Minecraft Forge 1.20.1)

Adds steel ore, steel tools, steel armor and a steel shield.

## Build

Requires a Java 17 JDK. From this folder:

- Windows: `gradlew build`
- Mac / Linux: `./gradlew build`

The first build downloads Minecraft's dev files (5-15 minutes). The mod ends up in
`build/libs/steelmod-1.0.0.jar`. Copy it into your `.minecraft/mods` folder and launch the Forge 1.20.1 profile.

To test without installing: `gradlew runClient`.

## What's in it

- **Steel Ore / Deepslate Steel Ore** - generates around y = 0 (veins between y -32 and 32, most common near 0).
  Needs an iron pickaxe or better. Drops Raw Steel (Fortune works, Silk Touch drops the ore).
- **Raw Steel -> Steel Ingot** - BLAST FURNACE ONLY. There are no furnace or smoker recipes.
- Steel Nugget, Steel Block, Block of Raw Steel (9 <-> 1 conversions like iron).
- **Tools**: sword, pickaxe, axe, shovel, hoe. 320 uses (iron 250), speed 6.5 (iron 6), +0.5 damage over iron.
- **Armor**: helmet, chestplate, leggings, boots. Durability x18 (iron x15), 16 total defense (iron 15), 0.5 toughness.
- **Steel Shield**: crafted like the vanilla shield, but with 1 steel ingot instead of 1 iron ingot.
  450 durability (vanilla 336). Repairs with steel ingots.

## Tuning

- Tool stats: `registry/ModTiers.java`
- Armor stats: `registry/ModArmorMaterials.java`
- Shield durability: `registry/ModItems.java` (`STEEL_SHIELD`)
- Ore rarity and height: `src/main/resources/data/steelmod/worldgen/placed_feature/steel_ore.json`
  (`count` = veins per chunk) and `configured_feature/steel_ore.json` (`size` = vein size).
- Existing worlds only get steel ore in chunks generated after the mod is installed.
