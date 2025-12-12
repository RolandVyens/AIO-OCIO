
# AIO OCIO

### 多合一色彩转换，适用于任何CG软件
======================
![OCIO](https://github.com/user-attachments/assets/1621e5e1-fb3b-4da5-8322-c8ab76396de3)

下载链接：https://github.com/RolandVyens/AIO-OCIO/releases/download/1.1.4/AIO-OCIO.zip

这个OCIO是基于Genco Uney的原版PixelManager修改而来，适用于Maya, Nuke, Houdini, C4D等一切CG软件。

https://github.com/Joegenco/PixelManager/

**你的软件必须支持OCIO 2.0标准才可以使用这个OCIO。**

======================

这个OCIO支持sRGB/Display P3/Rec1886/Rec2020的显示器，以下是在maya和nuke中的sRGB转换。

<img width="163" alt="屏幕截图 2024-07-20 230424" src="https://github.com/user-attachments/assets/8ede1bc8-c09a-4dee-870d-83ac9c1b5703">
<img width="245" alt="屏幕截图 2024-07-20 230534" src="https://github.com/user-attachments/assets/1a598e41-909d-437f-a9de-5ba399afb922">

#### 预制的配方: 

1. `config_CG_ACEScg.ocio`: 适用于完全支持ACEScg的任何CG软件。
2. `config_COMP_ACEScg.ocio`: 适用于合成软件，走ACEScg流程的项目。
3. `config_CG_Lin709.ocio`: 适用于Blender，工作色彩空间是Linear Rec709。
4. `config_COMP_Lin709.ocio`: 适用于合成软件，走线性709流程的项目，主要是配合Blender使用。

======================

### **使用方法:**

***对于常规软件:***

- 选择附带的OCIO其中之一设置为该软件的OCIO或加载进系统环境变量.

<img width="637" alt="屏幕截图 2024-07-20 233922" src="https://github.com/user-attachments/assets/139f78ed-df24-4b9a-8a2d-8e1cf4dfeea6">

***对于Blender:***

- 将压缩包内全部文件拷贝至blender datafiles文件夹下的colormanagement文件夹内，例如`C:\Users\XXX\AppData\Roaming\Blender Foundation\Blender\4.5\datafiles\colormanagement`
`
- 将`config_CG_Lin709.ocio`改名为`config.ocio`
<img width="757" alt="屏幕截图 2024-07-20 234945" src="https://github.com/user-attachments/assets/da857992-598f-4ff4-95b2-d1fe3218e6ad">
