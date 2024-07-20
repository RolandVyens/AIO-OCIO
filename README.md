
# PixelManager AIO OCIO

### All in 1 color I/O for Maya, Nuke, Houdini and more / 多合一色彩转换，适用于任何CG软件
======================

This OCIO is based on the origin PixelManager OCIO made by Genco Uney, optimized for general use in all kinds of CG software. 

https://github.com/Joegenco/PixelManager/

**Your software needs to support OCIO 2.0 in order to use this OCIO.**

======================

This OCIO supports Display of sRGB/Display P3/Rec1886/Rec2020, below are the sRGB view transforms in Maya and Nuke. 

#### Pre-made recipes: 

1. `config_CG_General.ocio`: For general CG softwares that have full supports of ACEScg.
2. `config_COMP_General.ocio`: For comp softwares, using ACEScg workflow.
3. `config_Blender.ocio`: For blender which working space is Linear Rec709.
4. `config_COMP_Blender.ocio`: For comp softwares, using Linear Rec709 workflow, mainly using with blender.

======================

### **Usage:**

***For General Softwares:***

Set this OCIO as the software's OCIO.

***For Blender:***

- Copy the files to the colormanagement folder under your blender install directory.
- Change the filename of  `config_Blender.ocio` to `config.ocio`