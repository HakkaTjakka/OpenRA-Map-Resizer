# OpenRA Map Resizer
 Resize OpenRA Map (Linux, c/c++, SFML)

```console
Syntax:
./red_alert resize <path to map.bin> <NEW_X_SIZE> <NEW_Y_SIZE>
Resizes the map map.bin to NEW_X_SIZE x NEW_Y_SIZE
map.yaml has to be edited manually to correct new x and y size at MapSize: and Bounds:


Syntax:
./red_alert insert <first path to map.bin> <second path to map.bin>
Inserts second map.bin into first map.bin
At top left.

Example:
./red_alert insert map2/map.bin map1/map.bin

For combining two maps:

1) First make room for the map you want to insert, into the map where you want to insert it into:
Example: 
./red_alert resize map2/map.bin 96 366
results in file: map.bin.resize
Move it to a dir (unpacked, not .oramap saved map) with the edited (Mapsize: and Bounds: set to new sizes) map.yaml and name it map.bin

2) Use OpenRA build in map editor to move the scenery down making room for the other map to be inserted at the top-left.
The coords in the map.yaml changes with all placed stuff when editing in-game.
Maybe also 'clear' the rest of the copied area. Save it.
Use the new map.bin to insert the other map into...

3) Insert the other map at the top-left
Example: 
./red_alert insert map2/map.bin map1/map.bin
results into file: map.bin.insert
This is the resulting map.bin
Now you have to manually edit the according map.yaml of the one you inserted into after moving it down with OpenRA map editor, and merge it with the map.yaml of the map inserted. You might add some player locations. If lots of actors help yourself.

INSERT PART OF MAP INTO ANOTHER MAP: 
Insert part of one map into another map. The location of the source will be placed at exact the same location of the destination map.
Syntax: insert-range
./red_alert insert-range <first path to map.bin> <second path to map.bin> <left> <top> <width> <height>
Example:
./red_alert insert-range map1/map.bin map2/map.bin 200 0 130 130
So first place the part of the map you want to insert into another map at the right location. Then note the left top (x,y) and width and height.
Use these with the insert-range command. The marked part of the second map will be inserted at the first map at the same location.
If you have any idea's please use the issues.
```
