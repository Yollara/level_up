# Level UP
Add a new mechanic to vintage story, a new level system to make your character stronger and efficient during the gameplay, making your feels you are progressing through the gameplay.

Features:
- GUI Level in chacter view
- Each tools has a chance to not use durability by the level you have for the specific tool
- Fully configurable

LEVELS:
- Hunter: Increases all damages sources to others creatures and players, earn xp by killing things
- Bow: Increases bow damages and reduce chance to lose arrows, earn xp by hitting and killing things with bows
- Cutlery: Increases knifes damages and harvest entity drops, earn xp by harvesting entities, hitting and killing things with knifes
- Spear: Increase spear damages, earn xp by hitting and killing things with spear
- Axe: Increases axes damages and mining speed, earn xp by chopping trees, breaking wood, hitting and killing things with axes
- Pickaxe: Increase pickaxes damages, ore drops and mining speed, earn xp by breaking stones, hitting and killing things with pickaxes
- Shovel: Increase shovels damages and mining speed, earn xp by breaking soil/gravel/sand, hitting and killing things with shovels
- Farming: Increase crop drop rate, earn xp by harvesting crops and till soils

Future features:
- Vitality system increasing hp.
- Vitality system increasing hp regen.
- Smithing specialist.
- Cooking specialist.
- Bow level increase precision.

https://github.com/LeandroTheDev/level_up/assets/106118473/8409a3ee-08ce-42b6-8747-aa7bf6405a26

### Observations
Integer limit, this mods saves the experience from the player as int, and C# integer limit is beyond the 2 billions, so if the player exp is reaching this number is quitly dangerous what would happen.

The nearest player in the cooking fire pit will receive the cooking experience when finish, if no players where found you will lose the experience.

This mod needs to be in both sides the client and server for working propertly, you can still build this only in server side, but some things will not work for example the mining speed mechanics will not work because the mining speed is handled by the client, also the level viewer will not be available for the clients.

Increase crop drop rate will only be increased if you harvest a crop with the final stage or the penultimate stage, the same for earning xp harvesting crops, harvesting crops in penultimate stage will decrease the experience gained.

Hunter level damage is increased before the tool damage level, so if you have 2x damage in hunter and 2x damage in spear and you have a spear with 4 damage the calculation is: (4 x 2) x 2 = 16

To change the configurations go to the mod folder in assets folders, if you want more informations you can see the [wiki](https://github.com/LeandroTheDev/levelup/wiki) to  know what each configuration does.

### Considerations
This mod changes a lot of native codes and can break easily throught updates.

Performances leaks can be apparent because of damage increase, drops rates system and level calculation, 
memory usage in the server can be slightly bigger because of static configurations.

Players with high numbers of levels can cause more cpu usage in the server side, and also the client when calculating the level.

### Building
Learn more about vintage story modding in [Linux](https://github.com/LeandroTheDev/arch_linux/wiki/Games#vintage-story-modding) or [Windows](https://wiki.vintagestory.at/index.php/Modding:Setting_up_your_Development_Environment)

Download the mod template for vintage store with name LevelUP and paste all contents from this project in there

> Linux

Make a symbolic link for fast tests
- ln -s /path/to/project/Releases/levelup/* /path/to/game/Mods/LevelUP/

Execute the comamnd ./build.sh, consider having setup everthing from vintage story ide before

> Windows

Just open the visual studio with LevelUP.sln

FTM License
