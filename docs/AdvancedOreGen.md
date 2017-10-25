<!-- TITLE: Advanced Ore Gen -->
<!-- SUBTITLE: A simple way to change the ore generator! -->

# Features
* nice looking GUI / Inventory
* no config.yml needed
* multiple generator presets for different permission
* support for sub ids
* works with ASkyBlock, AcidIsland and uSkyBlock
# Installation

There are some steps needed before AdvancedOreGen can be used.

### pre requirements

Before getting started, you need to have at least one of this plugins installed on your server:
* ASkyBlock (by tastybento)
* AcidIsland (by teastybento)
* uSkyBlock (by R4zorax)

### final installation

1. download the plugin .jar file that can be found at the following link:  https://www.spigotmc.org/resources/advancedoregen.40527/
2. drop the .jar file in your plugin folder
3. restart your server

# Configuration
The whole configuration is made through the GUI and by using certain commands.

### general generator behavior

The plugin allowes you to customize different generator presets for certain permission, thus for instance you're able to create a default generator generating cobblestone and a vip generator creating cobblestone and gold:

![minecraft screenshot](/img/h-1504395406-3250698-9-cf-0106826.png)

Generator #1 was set up with the permission `oregen.default` and Generator #2 with `oregen.vip`, therefor you need to provide the respective permission to your players.

Assuming the island owner has the permission `oregen.vip` and farms at a cobblestone generator, then the player would get the last configuration preset for which the player has permission.
That means the plugin basically iterates from left to right and checks if the player has permission and stops at the last generator.

Moreover, the plugin chooses the generator by the island owner's permission, not by the player that is mining.

### creating new generator presets

You can add new generators and it's permission by typing the following exemplary commands:

```yaml
/oregen generator add default oregen.default
/oregen generator add vip oregen.vip
```

where `default` and `vip` are the name of the generator preset and `oregen.default` and `oregen.vip` the permission.

After that, you may edit both generators by typing this command:

```yaml
/oregen edit
```

Now the GUI where you can choose the generator which you want to edit appears:

![H 1504395406 3250698 9 Cf 0106826](/uploads/h-1504395406-3250698-9-cf-0106826.png "H 1504395406 3250698 9 Cf 0106826")

Another GUI would pop up if you select a generator where you can put the blocks you want to be generated:

![H 1504396566 4427302 49223 Adfd 7](/uploads/h-1504396566-4427302-49223-adfd-7.png "H 1504396566 4427302 49223 Adfd 7")

The gold nugget indicates the current percentage, which should always be at 100.0, otherwise the plugin wouldn't work correctly.

Let's say we want this generator to create 50% cobblestone and 50% iron ore, we need to proceed the following steps:
1. select a cobblestone block and an iron ore block from your inventory (Add it before editing).
2. click on each block in order to change the percentage; a sign will be opened, put 50 in it
3. voila, your percentage should now be at 100.0.

![H 1504396945 2740433 76972 C 1346](/uploads/h-1504396945-2740433-76972-c-1346.png "H 1504396945 2740433 76972 C 1346")

![H 1504397137 2180880 3842 Fcdf 83](/uploads/h-1504397137-2180880-3842-fcdf-83.png "H 1504397137 2180880 3842 Fcdf 83")

Now you're ready to go and you are now able to customize the vip generator!

### AFK feature

Since version 1.3.2, AdvancedOreGen includes a nice anti afk features that allows you to give players who are mining AFK another generator.
AFK means, that the player doesn't changes his position during mining.
You can enable this by uncommenting the following lines in your config.yml:

```yaml
#afk-generator-name: afk
#afk-after-x-seconds: 1200
```

By default, the player is handled as AFK after 20 minutes. Keep in mind that you need to set up an AFK - Generator, which should have the afk-generator-name, the permission is inconsequential.

![H 1504396566 4427302 49223 Adfd 7](/uploads/afk-generator-example.png "Example of an AFK-Generator")


# Commands
There are some command for managing the different generators.

**Basic commands:**
`/oregen edit` - opens the GUI where you can choose the generator to edit
`/oregen edit <name>` - direct edits a generator (skips the selection GUI)

**Generator editing commands:**

`/oregen generator add <name> <permission>` - adds a new generatore preset with a defined permission
`/oregen generator remove <name>` - removed a generator preset
