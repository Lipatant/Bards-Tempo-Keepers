# EXPLANATION ON DATA FILES

## colors/*.bclr
Contains all colors used by palettes in <b>hex</b>.<br/>
<br/>
Example from beige.bclr:
>F0BC3C

## enemies/*.benm
Contains files used to code enemies.<br/>
The first line contains the name of the audio file,<br/>
The second one gives the health and attack.<br/>
<br/>
Example from morde.benm:
>Boss01<br/>
>2000   400

## events/*.evt
Contains 'objects' on the map<br/>
The first line gives the texture file as well as the texture coordinates,<br/>
The second line specify the color palette and layering informations.<br/>
Then, you'll have different instructions attached to the event:
- Always starting with a trigger: <b>>on_load</b>, <b>>on_tick</b>, <b>>player_contact</b>, <b>>player_interaction</b> or <b>>player_tile</b>.
- <b>COMMAND</b> if you want to specify the use of a single command instead of an entire script.
- Then finishing script. If you do use a command instead, use <b>`</b> (Ctrl+7) instead of spaces.

Example from player_cursor.bvnt:
>misc/overlay.png 1 0<br/>
>none 1 0<br/>
>\>on_load COMMAND set_palette_player`@0<br/>
>\>on_tick player/cursor_tp

## hitboxes/*.bhbx
Describes the shape of the hitbox of a tile with <b>0</b> (pass), <b>@</b> (block) or <b>.</b> (none).<br/>
Contains 8 lines of 8 characters.<br/>
<br/>
Example from fence_right_up.bhbx:
>........<br/>
>........<br/>
>........<br/>
>........<br/>
>........<br/>
>@@@@@@@@<br/>
>@@@@@@@@<br/>
>........<br/>

## items/*.btw
Contains every information to form an item.<br/>
The first line is always the name of the item,<br/>
The second corresponds to the type of item: <b>outfit</b> or <b>instrument</b>.<br/>
The third line is composed of a maximum of 3 components:
- The texture file of the outfit.
- The color palette to apply to the texture. By default, it will use the one corresponding to the player.
- A <b>no_skin</b> tag if the outfit ignores player's skin colour.

If it's an instrument, the fourth line will contains the audio file for fights. You can also add the volume with.<br/>
And the last line gives the health and attack bonus.<br/>
<br/>
Example from outfits/morde_golden_helmet.bitm:
>Morde's Golden Helmet<br/>
>outfit<br/>
>chars/helmet.png outfits/morde_iii no_skin<br/>
>none<br/>
>100 40 (+50%)

Example from instruments/glockenspiel.bitm:
>Glockenspiel<br/>
>instrument<br/>
>none<br/>
>note/iron_xylophone 150<br/>
>50 1

## maps/*.bmap
Maps files are used to, well, store maps.<br/>
The first 9 lines are used to give every layer, from .btlm files.<br/>
Theses are the following: ground, ground second, ground overlay, trees, trees overlay, walls, walls overlay, roofs and roofs overlay.<br/>
Then, the 10th line is used for the audio file.<br/>
<b>WORK IN PROGRESS</b>
