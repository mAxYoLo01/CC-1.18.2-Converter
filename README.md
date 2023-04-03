# CC-1.18.2-Converter
Converts Cubic Chunks Minecraft 1.12.2 worlds to Minecraft 1.18.2\
\
**Note** This will not convert everything, it is intended for conversion of BTE worlds, thus being tailored for creative building. Therefore any items stored in inventories and all entities will not be converted, it is likely that redstone circuits will also break.\
\
**Your Minecraft world height must be the exact same as the height set in the converter, else the plugin will not work!**\
\
To use the converter follow these steps:
- Download the Converter and Converter plugin of the same version in the releases section in this repository.
- Run the Converter jar using the command line, this is done using the following command: `java -jar CC-1.18.2-Converter.jar <path to input world> <path to output folder> <minY> <maxY> [number of threads]` minY and maxY must be the minimum and maximum height of the post-conversion world, these values must be within the limits of Minecraft [-2032,2016]. The number of threads you use will greatly effect the speed of the conversion, so use as many as your system can.
- Once the conversion is completed you'll have 3 folders `region`, this is the converted regions for Minecraft 1.18.2, `post-processing`, these will be needed in the next step and `entities`, this stored all the entity locations if you wanted to manually readd them.
- Using a Paper 1.18.2 server with the Converter plugin added you can open the world, don't forget to add the region files. The plugin will convert a lot of special blocks which have not already been converted, to use it set the world name in the `config.yml` and add the `post-processing` folder in the plugin folder (same as where config.yml is). The way the plugin works is that it'll only convert one region per 4 seconds and only regions that a player is currently standing in, this is to prevent loading chunks in other areas, which is very resource intensive for the server. Once a region is converted the file will be deleted from `/post-processing/`, so you'll be able to see what is left to be converted. If you want to help convert the regions by force you can teleport to the regions ingame, the x coordinate is the first number multiplied by 512 and the z the second number similarly multiplied by 512.
