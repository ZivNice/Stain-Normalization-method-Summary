# Stain-Normalization-method-Summary
# 染色归一化
## 基于计算的染色归一化

 ### 1. 病理染色工具整理
 |工具|概述|
 |-|:---|
 |[StainTools](https://github.com/Peter554/StainTools)|提供Reinhard、Macenko和Vahadane三种经典归一化工具|
 |[Stainlib](https://github.com/sebastianffx/stainlib)|Vahadane、Macenko和Reinhard、残差流进行可逆生成建模，4种染色归一化方法。其包含常用的一个组织图像输入库的颜色增强和归类方法，H&E 染色区域使用。不过Stainlib的颜色归一化有三种直接用StainTools
|[HistoCartography](https://github.com/histocartography/histocartography)|	Macenko和Vahadane,2种染色归一化方法。其包括一个管道运行器，它允许预定义管道步骤以及加载和保存实用程序，方便集成和减少重复代码。	示例有限，需要进一步适用深度学习模型
|[FalseColor-Python](https://github.com/serrob23/falsecolor)|	调整到虚拟H&E图像HSV颜色属性中位数	基于荧光的无透镜数字病理图	应用范围有局限
|[Histolab](https://github.com/histolab/histolab)|	Reinhard， Macenko和Vahadane，3种,histolab旨在处理 WSI、自动检测组织和检索信息图块，可集成到深度学习管道中。不过染色归一化模块还在开发中
|[HistomicsTK](https://github.com/DigitalSlideArchive/HistomicsTK)|	Reinhard 、Macenko，2种	提供经典的归一化、分割和分类。	提供的工具有限|
----
### 2.染色归一化文献代码

 1. **2016年，Structure-Preserving Color Normalization and SparseStain
    Separation for Histological Images，组织图像保持结构的颜色归一化和稀疏染色分离**

	该文详细介绍SNMF、SPCN和基于块实现的加速染色剂颜色基础估计的方案。[项目入口](https://github.com/abhishekvahadane/CodeRelease_ColorNormalization)

2. **2019年，STAINGAN: STAIN STYLE TRANSFER FOR DIGITAL HISTOLOGICAL IMAGES，染色:用于数字组织图像的染色样式转移**
评估我们的模型与Reinhard， Macenko， Khan和Vahadane的先进方法。代码受到[pytorch-DCGAN](https://github.com/pytorch/examples/tree/master/dcgan)和[CycleGAN](https://github.com/junyanz/CycleGAN)的启发

——————
持续更新中
