## what is this
repository to quickly setup a gmod dev envinroment without cloning twenty individual addons and dealing with conflicts  

## contains:

GCompute and co. - by notcake
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
