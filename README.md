
# PixelManager AIO OCIO

### All in 1 color I/O for Maya, Nuke, Houdini and more / 多合一色彩转换，适用于任何CG软件
======================

This OCIO is based on the origin PixelManager OCIO made by Genco Uney, optimized for general use in all kinds of CG software. 

https://github.com/Joegenco/PixelManager/

**Your software needs to support OCIO 2.0 in order to use this OCIO.**

======================

This OCIO supports Display of sRGB/Display P3/Rec1886/Rec2020, below are the sRGB view transforms in Maya and Nuke. 

<img width="163" alt="屏幕截图 2024-07-20 230424" src="https://github.com/user-attachments/assets/8ede1bc8-c09a-4dee-870d-83ac9c1b5703">
<img width="245" alt="屏幕截图 2024-07-20 230534" src="https://github.com/user-attachments/assets/1a598e41-909d-437f-a9de-5ba399afb922">

#### Pre-made recipes: 

1. `config_CG_General.ocio`: For general CG softwares that have full supports of ACEScg.
2. `config_COMP_General.ocio`: For comp softwares, using ACEScg workflow.
3. `config_Blender.ocio`: For blender which working space is Linear Rec709.
4. `config_COMP_Blender.ocio`: For comp softwares, using Linear Rec709 workflow, mainly using with blender.

======================

### **Usage:**

***For General Softwares:***

- Set one of the OCIOs as the software's OCIO or set as system Environment Variable.

<img width="637" alt="屏幕截图 2024-07-20 233922" src="https://github.com/user-attachments/assets/139f78ed-df24-4b9a-8a2d-8e1cf4dfeea6">

***For Blender:***

- Copy the files to the colormanagement folder under your blender install directory.
- Change the filename of  `config_Blender.ocio` to `config.ocio`
<img width="757" alt="屏幕截图 2024-07-20 234945" src="https://github.com/user-attachments/assets/da857992-598f-4ff4-95b2-d1fe3218e6ad">
