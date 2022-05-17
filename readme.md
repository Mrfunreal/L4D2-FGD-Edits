# L4D2-FGD-Edits
This is a collection of FGD edits that can be put together to make L4D2's Hammer easier to use and more useful. 

It adds a lot of options to various entities to make them more useful.

### Contains
"Fade Distance" sphere helper to areaportal_window entities so you can easier pick where the fade starts and ends.
Ammo upgrade entities as already deployed versions
New visgroups for many type of entities
Default models for many props, like weapon_ammo_spawn, trigger_finale...
More useful melee spawner that lists all usable melee weapon names in the help box, to copypaste names.
A whole lot of entity fixes specific for L4D2

Contains a VPK for hammer, including:
Tool textures specifically for every kind of tool brush entity. like trigger_once, trigger_hurt, info_changelevel...
A lot of new sprites for entities that didn't have one. Like the director and icons for all three tonemap entities.
various differently colored sprites for logic_relay. For people who like to color code their things.
L4D2 specific measure textures for doors, jump height, crouch space...

### Install
1. Download the entire "L4D2-FGD-Edits" repo folder into ```Steam\steamapps\common\Left 4 Dead 2\bin```
2. You should end up with the directory ```Steam\steamapps\common\Left 4 Dead 2\bin\L4D2-FGD-Edits```
3. In hammer click on ``Tools - Options``
4. In the "Game Configuration" tab, look for the "Game Data Files" box use ONLY te left4dead2_ADDON.fgd.
5. Copy the ``Hammer_vpk`` folder into l4d2's Root folder. next to  left4dead2.exe and the dlc folders.
6. Open the ``left4dead2`` folder and the Gameinfo.txt inside.
7. Scroll down to the first few ``game`` lines.
```
Game	update
Game	left4dead2_dlc3
Game	left4dead2_dlc2
Game	left4dead2_dlc1
Game	|gameinfo_path|.
Game	hl2```

8. Add the folowing above ``Update``
```Game hammer_vpk```