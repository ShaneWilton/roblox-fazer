# Cure Framework

**Cure** is a solution to Roblox's lack of library system. It constructs a .rbxm file from a source tree, to be inserted into the ServerScriptService.

### Structure

- `README.md`

	This file!

- `source`

	Contains the source code for Cure scripts as well as the structure of the
	Cure framework.

- `build`

	Contains the .rbxm file created by `build.lua`.

- `build.lua`

	Compiles everything in the `source` folder into a .rbxm file. All files
	and folders become Roblox instances. Folders are converted into
	Configuration objects, and files are converted based on their extensions.
	The name of a file or folder is used as the name of the object.

	- `*.script.lua`: Converts to a Script source.
	- `*.localscript.lua`: Converts to a LocalScript source.
	- `*.modulescript.lua`: Converts to a ModuleScript source.

	For convenience, Lua files are checked for syntax errors. Note that a file
	with an error will still be built regardless.

	The output file name can be specified by giving it as an option to
	build.lua. Defaults to "cure.rbxm".

		lua build.lua [filename]
