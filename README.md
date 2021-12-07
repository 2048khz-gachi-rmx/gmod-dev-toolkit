## what is this
repository to quickly setup a gmod dev envinroment without cloning twenty individual addons and dealing with conflicts  

## contains:

GCompute and co. - by [notcake](https://github.com/notcake/)
> [Gooey](https://github.com/notcake/gooey)     
> [GLib](https://github.com/notcake/glib)       
> [GCompute](https://github.com/notcake/gcompute)  
> [VFS](https://github.com/notcake/vfs)       
> [GCodec](https://github.com/notcake/gcodec)  
> 
> _i personally use gcompute for the cool table printing,_  
> _but rumors say it has an in-game IDE..._


------

_for seeing serverside console output on clients (with admin priviliges)_  
[EPOE](https://github.com/Metastruct/EPOE) - by [Metastruct](https://github.com/Metastruct/)    

_for running lua easily, be it through chat or straight from your text editor (with admin priviliges)_  
[luadev](https://github.com/Metastruct/luadev) - by [Metastruct](https://github.com/Metastruct/)  


_because the other addons use aowl as an admin mod_  
castrated [aowl](https://github.com/2048khz-gachi-rmx/fast_addons) - [original](https://github.com/CapsAdmin/fast_addons) by
  [CapsAdmin](https://github.com/CapsAdmin/), edited by me  

## installation:
1) `git clone https://github.com/2048khz-gachi-rmx/gmod-dev-toolkit.git --recursive`  
_downloading via web won't work because it won't download submodules (because github is cringe)_

2) move all folders from the cloned repository into `addons/`

3) **[recommended]**  
Move `EPOE/lua/bin` into your server's `lua/bin` (if the folder doesn't exist, create it)  
_this will allow the server to send clientside errors and other neat stuff to the EPOE console_

4) **[optional]**  
Check out [luadev](https://github.com/Metastruct/luadev)'s installation guide: following through with it will allow you to execute lua files straight from your text editor

## getting started
If you don't have an admin mod handling ranks for you, you'll need to set yourself to superadmin rank, and you'll need to do this on every server startup. Get a proper admin mod if you don't wanna do that.  
`aowl rank part_of_name superadmin` in the server console will do the trick.

`epoe_login` in console to log into EPOE, if you were denied access at first. You can use `+epoe` for more customization.

#### Lua commands:
> Most commands support shortcuts: `me` will be your player object, `this` will be whatever you're looking at, `there` will be the position you're looking at, etc.  
> Entities can be indexed by their entity index using `_0` (equivalent of Entity(0))  
> Players and entities can be indexed by part of their name (eg `.p rub` will try to match a player with `rub` in their name or an entity with `rub` in their class name) 

**`.l [code]`** - runs Lua code on the server (eg: `.l print(123)` will print 123 on the server)  
**`.p [expression]`** - prints a value from the server (eg: `.p me` will print your player's table)  
**`.lc [code]`** - runs Lua code on all clients (eg: `.lc RunConsoleCommand("kill")` will make everyone lowtiergod themselves)  
**`.pc [code]`** - prints a value from all clients (eg: `.pc input.LookupKeyBinding(KEY_G)` will tell you everyone's binds on G)  
**`.lm [code]`** - runs Lua code on you (eg: `.lm RunConsoleCommand("kill")` will lowtiergod you)  
**`.tm [code]`** or **`.pm2 [code]`** - prints a value from your client (eg `.tm input` will print the contents of the `input` library)  
**`.lsc [player] [code]`** - runs Lua code on just the matched player (eg `.lsc weezerfan RunConsoleCommand("kill")` will make someone with `weezerfan` in their name lowtiergod themselves)  
**`.psc [player] [code]`** - prints a value from the matched player (eg `.psc weezerfan preferredAlbum` will return the global `preferredAlbum` variable on their client)  

#### Admin abusing commands:
**`.go/goto/owo/warp [entity]`** - teleports you to the matched entity  
**`.tp`** - teleports you to where you're looking  
**`.send [who] [where]`** - teleports the `who` entity to the `where` entity  
these have support for special waypoints: "spawn" will respawn the player  
**`.give (player) [class]`** - tries to find a weapon with a matching classname and give it to the player (you if unspecified)  
> _`.give 357` will give you a magnum; `.give weezerfan 357` will give weezerfan a magnum; `.give #all rpg` will give everyone an rpg_  

// more needs documenting... //
