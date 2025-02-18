## [![Icon](./icon/icon_32x32.png)](.) Demucs GUI
[![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/CarlGao4/Demucs-GUI?include_prereleases&style=plastic)](https://github.com/CarlGao4/Demucs-Gui/releases) 

This is a GUI for music separation project `demucs`.

I created this fork from Version 1.3.1 (Linux/CPU/AppImage) to experiment with and customize GUI behavior.  

Changes to GUI:

1.  The previously loaded model is saved to the settings.json file and auto-loaded on startup.

2.  The Select Model tab stays enabled, so new models can be loaded without restarting the application. 

3.  Since the Mixer tab has to be replaced when a new model is loaded, I moved it to the last position.  There is no PyQt6 builtin .replaceTab function for existing tabs, so I use .removeTab then .addTab, so the Mixer tab is the last tab.

4.  The main window geometry is saved and recalled from settings.json ("mainGeometry":"[<x>, <y>, <w>, <h>]").  

5.  (Optional) The debug menu can be enabled by adding "debug":true to settings.json file.

6.  (Optional) A custom style can be applied to the application by adding "customStyle":"<your css styles>" to settings.json file.  For example, "customStyle":"QWidget {color: 'black';}", would apply a black font to all QWidgets.  I added this option because some of the stock widget fonts were not visible on my PC.

The program should run unaffected if optional items are left unset.

I may try other changes in the future.

If you would like to experiment with the program, extract the contents of the appimage using the --appimage-extract option.  This saves the entire contents of the appimage to the squashfs-root folder, where you can run the program from, and make changes.  To repack the AppImage, use the appimagetool (https://github.com/AppImage/appimagetool).


## Acknowledgements
This project includes code of [Demucs](https://github.com/adefossez/demucs) under MIT license.
