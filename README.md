# VoxCharger #

- **Author**: CXO2, 天音あめ
- **Email**: com@cxo2.me, i@amane-a.me
- **Version**: 0.9.9b

Recharge your KFC Chicken sauce ([Download](https://github.com/SirusDoma/VoxCharger/releases))   

Written under C# language, this program allow you to manage music asset files of your KFC installation.  
Additionally, it include built-in converter to import ksh into vox that can be consumed by KFC.  

If you're not familiar with these file formats, then this sauce is not for you.

## Prerequisite ##

### .NET Framework 4.7
This program require .NET Framework 4.7 in order to run properly.

### Latest datecodes or newer only
Latest omnimix structures is slightly changed compared to previous datecodes, it won't load anything that doesn't match with `2020011500` structure.  

### Backup
Backup your data before using this program, it able to modify and delete your music assets.  
Keep in mind that the program won't allow you to make any changes against original mix.

### No IFS Support
Use [IFS LayeredFS](https://github.com/mon/ifs_layeredfs) in your KFC installation. This program will not pack your assets into IFS, nor attempt to process existing ones. 
When mix with ifs files is selected, the program won't be able load music assets properly.  

If you need to pack your music assets into ifs, use another tool that process ifs file (for an instance: [mon ifs tools](https://github.com/mon/ifstools)).

### 2DX Tools
Make sure that mon `2dxwavconvert.exe` and `2dxbuild.exe` are placed in the same directory along with the program.  
Can't find it? you can grab the tools [here](https://github.com/mon/2dxTools/releases).

## Remarks ##

### Mix Lock
Original mix is locked to prevent you (yes, you) to break your KFC installation.  
Again, use [IFS LayeredFS](https://github.com/mon/ifs_layeredfs). If you haven't heard this then you're totally missing out!

### Conversion Output
Vox have some sense in it's file format than ksh file, as the result, not all attributes can be mapped precisely and potentially lead into bug in the output file. For FX mapping, user defined FX will be ignored, only basic FX's that will be included into the output.  

Remember, stupid input get stupid output. But if you believe it's a bug, feel free to open issue or PR.

### Network Scores
Make sure you are using under Offline environment and **NOT** connected to any KFC network server while using the output files of this tool. It could break network score table and you may get banned from the network for doing so.

### Music DB
The program also prevent you to modify Music ID and some attributes are kept hidden from editor, For existing songs, some of their attributes might untouched throughout save iteration, but the rest of hidden attributes might be replaced with dummy / stub data. 

If this really concern you, make sure to backup your `music_db.xml` / `music_db.merged.xml`.

### Music Preview
Imported music preview from normal audio files may broken or not trimmed properly in the output file. Preview offset in ksh is also ignored, you need dedicated preview file with proper fade in and out.  

Keep in mind that `2dxwavconvert.exe` will not do this for you, it only trim your audio into 10 second for preview purpose. Until program supports built in encoder, you have to provide 2dx preview manually for proper preview file.  

If you can't live without it, consider making PR to this feature.

### Asset File Modification
Replacing asset files such as vox, 2dx and graphic files are happen immediately after changes are confirmed. In other hand, metadata need to be saved manually by clicking `File -> Save` or `CTRL+S`.  

Note that you can postpone asset modification until you save metadata by disabling autosave in `Edit -> Autosave Assets`

# License #

This is an open-sourced application licensed under the [MIT License](http://github.com/SirusDoma/VoxCharger/blob/master/LICENSE)
