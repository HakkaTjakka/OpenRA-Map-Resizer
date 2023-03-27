# OpenRA Map Resizer
 Resize OpenRA Map (Linux, c/c++, SFML)

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
Move it to a dir (unpacked, not .oramap saved map) with the original map.yaml and name it map.bin

2) Use OpenRA build in map editor to move the scenery down making room for the other map to be inserted at the top-left.
The coords in the map.yaml changes with all placed stuff. Maybe also 'clear' the rest of the copied area. Save it.
Use the new map.bin to insert the other map into...

3) Insert the other map at the top-left
Example: 
./red_alert insert map2/map.bin map1/map.bin
results into file: map.bin.insert
This is the resulting map.bin
Now you have to manually edit the according map.yaml of the one you inserted into after moving it down with OpenRA map editor, and merge it with the map.yaml of the map inserted. You might add some player locations. If lots of actors help yourself.
