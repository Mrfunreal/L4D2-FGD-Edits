This project modifies the entire FGD of L4D2 to improve the mapping experience.<br>
It also adds tool textures to differentiate all brush entities you want to use.<br>
Includes Hammer++ and Tools++ additions, which have also been modified for even better QOL.<br>

Some examples include:<br>
- Worldspawn entity that lets you pick Skybox, music string, and daytime from a dropdown.<br>
- Func_areaportal window with added distance pickers.<br>
- New and modified helper models/sprites<br>
- Further explanations of obtuse keyvalues.<br>
- More autovisgroups<br>
- Frustums for all camera entities<br>




⚠️ **$${\color{red}Warning:}$$**<br> 
You must change the default entity from info_survivor_position to info_player_start, or another entitiy without a model!<br>
Swapping from any entity with a model to an entity that now got a helper model -when it previously did not have one- can cause crashes.

### Install
1. Download the latest release's "Source Code" into ```Steam\steamapps\common\Left 4 Dead 2\bin```
2. Create a folder named L4D2-FGD-Edits, unpack the contents of the zip into that folder.<br>
   (Hammer_vpk, Detailtype_helper, Left4dead2_ADDON.fgd, Visgroups.fgd)
4. You should end up with the directory ```Steam\steamapps\common\Left 4 Dead 2\bin\L4D2-FGD-Edits```<br>
5. In hammer click on **Tools - Options**
6. In the "Game Configuration" tab, look for the "Game Data Files" box use **ONLY** the left4dead2_ADDON.fgd.<br>
Even if Tools++ is installed. Its FGD edits are incorporated here.

 <img src="pictures/hammer_config.png" width=234/>
 
6. Open  ```Steam\steamapps\common\Left 4 Dead 2\left4dead2\Gameinfo.txt```
7. Scroll down to the first few **game** lines.
```
Game	update
Game	left4dead2_dlc3
Game	left4dead2_dlc2
Game	left4dead2_dlc1
Game	|gameinfo_path|.
Game	hl2
```
8. Add the folowing above **Game Update**

```Game	bin\L4D2-FGD-Edits\hammer_vpk```

## See Also:
* [Easy Navmesh Edit CFG files](https://www.github.com/Mrfunreal/L4D2_Navmesh_CFG "L4D2_Navmesh_CFG")
* [Autocompiler batch script](https://github.com/Mrfunreal/Various_Scripts/blob/main/Source%201/Hammer_Autocompile.bat)
  

# Images
<details>
<p>Generic helper models for randomized weapon spawns.</p>
<img src="pictures/generic_helpers.png"/>
<p>Better Axis helper</p>
<img src="pictures/AxisHelper.gif"/>
<p>Colorable helpers</p>
<img src="pictures/Colorable_helpers.png"/>
<p>Custom helper for Vrad++ light_projected</p>
<img src="pictures/light_projected_edit.png"/>
<p>hlp_origin_vector to get values for vscripts</p>
<img src="pictures/origin_vector_helper.png"/>
<p>Cubemap Helpers.</p>
<img src="pictures/cubemap_helper.jpg"/>
<p>Info_survivor_position with helper models. </p>
<img src="pictures/info_survivor_position.png"/>
<p>more tool textures</p>
<img src="pictures/tooltextures.png"/>
<p>Color codiing *some* entities</p>
<img src="pictures/colorcoding.png"/>
<p>hlp_player_scale_measure to easily model narrow spots</p>
<img src="pictures/playerscale_measure.png"/>
<p>connecting lines for ropes in Hammer++</p>
<img src="pictures/ropelines.png"/>
<p>Areaportal Distance Picker.</p>
<img src="pictures/areaportalwindow.gif"/>
<p>Already deployed upgrades.</p>
<img src="pictures/already_deployed_upgrades.png"/>
<p>More Visgroups.</p>
<img src="pictures/visgroups.png"/>
<p>Better Melee spawn.</p>
<img src="pictures/melee_spawn.png"/>
<p>Obsolete's unused or not programmed entities.</p>
<img src="pictures/Obsoleter.png"/>
<p>New icon sprites.</p>
<img src="pictures/sprites.png"/>
<img src="pictures/relays.png"/>
<p>Worldspawn settings.</p>
<img src="pictures/witch_behaviour.jpg"/><br>
<img src="pictures/skybox_picker.jpg"/><br>
<img src="pictures/music_picker.jpg"/><br>
<img src="pictures/detail_picker.jpg"/>
<p>Damage Types</p>
<img src="pictures/damagetypes.jpg"/>
<p>Blend Textures displaying what detail they use.<br>Doesn't work in Hammer++!</p>
<img src="pictures/blendtextures.jpg"/>
</details>

# Documentation of the FGD Edits:
*Theres many small edits that are not documented, because i honestly forgot to document them.*
## New Base Entities
- Classname        	- Just to easily add this function to entities
- LagCompensate    	- Just to easily add this function to entities
- ThinkFunction    	- Just to easily add this function to entities
- WeaponSpawnCarry	- A base for Carryable weapons
- WarnBBox			- Adds warning about brush entity using the BBox. Meaning you're unable to use diagonal brush entities.

## New Point Entities
- hlp_origin_Vector - Just gives you the origin of where this entity is and gives you a radius option. Only useful for getting vectors for Vscripts.
- weapon_gascan         	- Usually you'd have a prop_physics using desired model.
- weapon_gnome          	- Usually you'd have a prop_physics using desired model.
- weapon_cola_bottles		- Usually you'd have a prop_physics using desired model.
- weapon_fireworkcrate		- Usually you'd have a prop_physics using desired model. (Does not explode until picked up first)
- weapon_oxygentank			- Usually you'd have a prop_physics using desired model. (Does not explode until picked up first)
- weapon_propanetank		- Usually you'd have a prop_physics using desired model. (Does not explode until picked up first)
- upgrade_laser_sight		- Spawnpoint for JUST the laser.
- upgrade_ammo_incendiary	- Already deployed Incendiary ammo.
- upgrade_ammo_explosive	- Already deployed explosive ammo.

## FGD Edits:
- Areaportals
	- Added sphere for easy setup of fade distances.
- Cubemap
	- Added 512x512, 1024x1024x 2048x2048 resolution.
- Damagetype
	- Properly documented existin damage types.
	- Added unused damage types.
	- Trigger_hurt, trigger_hurt_ghost, point_hurt, and filter_damage_type make use of the new damage types.
- Func_block_charge
	- Remade fgd entry to only contain parts this entity actually uses.
	- Added warning about this brush using AABB/BBOX.
- Info_game_event_proxy
	- Added all existing game events to a drop down list, so you can pick which to use.
- Navattributeregion
	- Added all usable nav attributes.
- Info_survivor_position
	- New helper model.
	- Being able to pick model, survivor name and gamemodes from a dropdown.
- Prop_physics
	- Added parentname
	- The model window has a note listing all carryable items models, to copypaste into model field.
- Prop_static_base
	- Made "disablevertexlighting" to be off by default.
- Prop_door_rotating
	- Spawns with a model of a door 
	- Made "Hinge Axis" obsolete, as it didn't do anything to begin with.
- Prop_door_rotating_checkpoint 
	- Same changes as prop_door_rotating
	- The model window has a note listing all saferoom doors, to copypaste into model field.
- Color_correction
	- Added tip notes and obsoleted things.
- Func_fish_pool
	- Added helper sphere to see how large the pool is.
- Env_smoketrail
	- Added sphere for spawnradius.
- Env_physics_blocker & env_player_blocker
	- Changed size of box
- func_lod & env_fire
	- Adds classname, lagcompensate keyvalues
- logic_auto
	- Removed useless global states. L4d2 has none. 
- Trigger_finale
	- Hamradio as default radio.
- prop_car_glass & prop_car_alarm
	- Made entities use the only models they always use as default model. Way easier to setup now.
- TriggerOnce
	- Listed obsolete flags as obsolete (Applies to all triggers)
- WeaponSpawnSingle
	- Renamed WeaponSkin, to make it more obvious what it is. Applies to all weapon spawns. (Skin and Weaponskin are not the same, but you need to edit both.)
- weapon_spawn
	- Added generic weapon helper model
- weapon_ammo_spawn
	- The model window has a note listing both ammo models, to copypaste into model field.
- weapon_melee_spawn
	- Added ability to pick helper model from list.
	- Added model browser to browse for custom melee models, to copy paste into helper model field.
	- Added a note about what melee weapon names are valid
- prop_minigun_l4d1 & prop_mounted_machine_gun
	- Removed prop_dynamic as base, because none of its keyvalues affect the mounted weapons.
- Worldspawn
	- Removed obsolete keyvalues.
	- Made DetailMaterial a drop down to pick from possible detail material files.
	- TimeOfDay only affects if the witch sits or stands. So i renamed it and turned it into a drop down menu to pick Witch behaviour.
	- Turned MusicPostFix into a dropdown to pick music type.
	- Turned SkyName into a dropdown to Skybox texture.
- Visgroups
	- Added a whole lot of visgroups for various entities.
- func_nav_avoidance_obstacle
	- Added warning about this brush using AABB/BBOX.
- func_detail_blocker
	- Added warning about this brush using AABB/BBOX.

## Other edits
- Tool textures specifically for every kind of tool brush entity. like trigger_once, trigger_hurt, info_changelevel...
- Entirely new tool texture: ToolsNonsolidButton. A texture that is not solid, does not cut visleafes and is invisible. Perfect for buttons that you would need to clip through, or don't want the collision of the brush entity to be a factor. (Does not need to be shipped with the map.)
- A lot of new sprites for entities that didn't have one. Like the director and icons for all three tonemap entities.
- Various differently colored sprites for logic_relay. For people who like to color code their things.
- L4D2 specific measure textures for doors, jump height, crouch space...
- Added **alleydirt_leaves** and **urban_overgrown_docks** $detailtype, with the required **detail.vbsp**
- Added "tool" keyword to Scavengeboundary texture  TankWall texture. (use the material keywork search, not material name search.)

## New / Better Helpermodels
- Weapon_Item_Spawn 
- Info_Zombie_Spawn
- Info_Survivor_Position
- Commentary_Zombie_Spawner
- Point_Viewcontrol_Multiplayer
- Point_Viewcontrol_Survivor
- Point_Deathfall_Camera
- Info_Teleport_Destination
- Upgrade_Spawn
- Env_Steam
- Sky_Camera
- Env_Lightglow
- Point_Spotlight
- Beam_Spotlight
- Light_Spot
- Path_Track
- Move_Track

## New Sprites
- Point_Nav_Attribute_Region
- Env_Tonemap_Controller_Infected
- Env_Tonemap_Controller_Ghost
- Postprocess_Controller
- Info_Director
- Light_Directional
- Env_Sun
- Info_Map_Parameters
- Info_Map_Parameters_Versus
- Logic_Relay
- Point_Clientcommand
- Point_Servercommand
- Point_Broadcastclientcommand
- Info_Goal_Infected_Chase
- Env_Texturetoggle
- Info_Remarkable
- Env_Entity_Maker
- Ambient_Music
- Point_Script_Use_Target
- Point_Prop_Use_Target
- Info_Target_Instructor_Hint
- Env_Detail_Controller
- Path_Track
- Info_Elevator_Floor


