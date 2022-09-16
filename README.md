# 染色归一化

 ## 1. 病理染色工具整理
 |工具|概述|
 |-|:---|
 |[StainTools](https://github.com/Peter554/StainTools)|提供Reinhard、Macenko和Vahadane三种经典归一化工具|
 |[Stainlib](https://github.com/sebastianffx/stainlib)|Vahadane、Macenko和Reinhard、[残差流](https://github.com/sara-nl/color-information)进行可逆生成建模，4种染色归一化方法。其包含常用的一个组织图像输入库的颜色增强和归类方法，H&E 染色区域使用。不过Stainlib的颜色归一化有三种直接用StainTools
|[HistoCartography](https://github.com/histocartography/histocartography)|	Macenko和Vahadane,2种染色归一化方法。其包括一个管道运行器，它允许预定义管道步骤以及加载和保存实用程序，方便集成和减少重复代码。	示例有限，需要进一步适用深度学习模型
|[FalseColor-Python](https://github.com/serrob23/falsecolor)|	调整到虚拟H&E图像HSV颜色属性中位数	基于荧光的无透镜数字病理图	应用范围有局限
|[Histolab](https://github.com/histolab/histolab)|	Reinhard， Macenko和Vahadane，3种,histolab旨在处理 WSI、自动检测组织和检索信息图块，可集成到深度学习管道中。不过染色归一化模块还在开发中
|[HistomicsTK](https://github.com/DigitalSlideArchive/HistomicsTK)|	Reinhard 、Macenko，2种	提供经典的归一化、分割和分类。	提供的工具有限|
|[QuPath](https://github.com/qupath/qupath)|提供Ruifrok 和 Johnston 介绍的颜色反卷积方法，QuPath提供了一套强大的工具来处理WSI图像,缺点是没有python接口，java编写，很难应用到当前的深度学习框架中，不过做项目的方法可以学习
|[CellProfiler](https://github.com/CellProfiler/CellProfiler)|CellProfiler是一款免费的开源软件，旨在使生物学家无需接受过计算机视觉或编程培训，即可自动定量测量数千张图像中的表型。|
----
## 2.染色归一化文献代码

 1. **2016年，Structure-Preserving Color Normalization and SparseStain
    Separation for Histological Images，组织图像保持结构的颜色归一化和稀疏染色分离**

	该文详细介绍SNMF、SPCN和基于块实现的加速染色剂颜色基础估计的方案。**基于matlab** [【代码入口】](https://github.com/abhishekvahadane/CodeRelease_ColorNormalization)

2. **2019年，STAINGAN: STAIN STYLE TRANSFER FOR DIGITAL HISTOLOGICAL IMAGES，染色:用于数字组织图像的染色样式转移**
评估我们的模型与Reinhard， Macenko， Khan和Vahadane的先进方法。代码受到[pytorch-DCGAN](https://github.com/pytorch/examples/tree/master/dcgan)和[CycleGAN](https://github.com/junyanz/CycleGAN)的启发。[【代码入口】](https://github.com/xtarx/StainGAN)


3. **2019年，Fast GPU-Enabled Color Normalization of Whole Slide Images in Digital Pathology快速gpu支持的数字病理颜色归一化**
本文对结构保持颜色归一化(SPCN)算法进行了改进。1）SPCN在颜色基估计方面偶尔会出现错误，导致产生假象，比如在污渍之间交换颜色基向量，或者在没有组织的情况下给背景添加颜色色调。2）由于运行时间长、使用专有软件平台和库以及无法自动处理WSIs，原始的SPCN代码在10亿像素的全幻灯片图像(WSIs)上不能轻易使用。完全重写软件，去自动处理流行WSI格式的任何大小的图像。[【代码入口】](https://github.com/MEDAL-IITB/Fast_WSI_Color_Norm)

4. **2020年，Pix2Pix-based Stain-to-Stain Translation: A Solution for Robust Stain Normalization in Histopathology Images Analysis基于pix2像素的染色到染色转换:组织病理学图像分析中稳健染色归一化的解决方案**
 染色-染色转换(STST)方法用于苏木素和伊红(H&E)染色的组织病理学图像的染色归一化，不仅学习特定的颜色分布，而且保留相应的组织病理学模式。我们基于“pix2pix”框架执行翻译过程，该框架使用条件生成器对抗网络(cga)。[【代码入口】](https://github.com/pegahsalehi/Stain-to-Stain-Translation)
 5. **2021年，Blind color deconvolution, normalization, and classification of histological images using general super Gaussian priors and Bayesian inference，利用一般超高斯先验和贝叶斯推理对组织图像进行盲颜色反褶积、归一化和分类**
将提出的SG框架与文献中常用的(B)CD方法进行比较:Ruifrok和Johnston的经典非盲CD方法，以及Macenko等人，Vahadane等人，Alsubaie等人，Hidalgo-Gavira等人[25]，Pérez-Bueno等人和Zheng等人的BCD方法。分别用RUI、MAC、VAH、ALS、HID、PER和ZHE表示。**基于matlab**，[【代码入口】](https://github.com/vipgugr)
 6. **2021年，SA-GAN: Stain Acclimation Generative Adversarial Network for Histopathology Image Analysis，SA-GAN:染色训练生成对抗网络用于组织病理学图像分析**
 在染色归一化中，很多方法依赖于单一的参考图像，而不是纳入整个数据集的颜色分布。在本文中，设计了一种新的基于机器学习的模型，它利用了单个目标图像的整个数据集分布和颜色统计，而不是只依赖于单个目标图像。[【代码入口】](https://github.com/tasleem-hello/SA-GAN/tree/main)
 7. **2021年， StainNet: A Fast and Robust Stain Normalization Network，StainNet:一个快速和稳健的染色归一化网络** 
使用蒸馏学习来降低深度学习方法的复杂性，并使用一个名为StainNet的快速鲁棒网络来学习源图像和目标图像之间的颜色映射。StainNet可以从整个数据集中学习颜色映射关系，并以像素对像素的方式调整颜色值。像素到像素的方式限制了网络大小，并避免了样式转换中的工件。在细胞病理学和组织病理学数据集上的结果表明，StainNet可以达到与基于深度学习的方法相当的性能。计算结果表明，StainNet比StainGAN快40倍以上，可以在40秒内归一化10万× 10万张幻灯片图像。[【代码入口】](https://github.com/khtao/StainNet)

8. **2021年，Single image super-resolution for whole slide image using convolutional neural networks and self-supervised color normalization利用卷积神经网络和自监督颜色归一化实现全幻灯片图像的单图像超分辨率**
一种基于深度学习的方法，利用单图像超分辨率(SISR)从低分辨率输入重建高分辨率的组织学图像。进一步提出了一种自我监督的颜色归一化方法，可以去除染色变异伪影。全面性评价表明，通过结合颜色归一化方法，SISR框架可以很好地推广从其他患者组织队列中收集的未见数据。[【代码入口】](https://github.com/uw-loci/demo_wsi_superres)
9. **2021年，Self-Attentive Adversarial Stain Normalization，自我注意对抗性染色正常化**
传统的染色规范化和颜色增强策略可以处理人类水平偏差。但深度学习模型可以很容易地分解这些方法中使用的线性变换，导致不必要的偏见和缺乏泛化。为了处理这些限制，该文提出了一种自我注意对抗性染色归一化(SAASN)的方法，将多个染色外观归一化到一个共同的领域。[【代码入口】](https://github.com/4m4n5/saasn-stain-normalization)
10.  **2021年，Normalization of HE-stained histological images using cycle consistent generative adversarial networks，使用循环一致生成对抗网络对he染色组织学图像的归一化**
研究了CycleGAN(循环一致生成对抗网络)在苏木素-伊红染色的组织学图像中用于颜色归一化的潜力，使用日常临床数据并考虑内部染色方案变化的可变性。[【代码入口】](https://github.com/m4ln/stainTransfer_CycleGAN_pytorch)
11. **2022年，RandStainNA: Learning Stain-Agnostic Features from Histology Slides by Bridging Stain
Augmentation and Normalization，RandStainNA:通过染色增强和归一化结合从组织学切片中学习染色不可知的特征**
RandStainNA适用于HED, HSV, LAB等一系列颜色空间的染色规范化。采用**reinhard**方法进行染色归一化。[【代码入口】](https://github.com/yiqings/RandStainNA)
12. **2022年，Staining condition visualization in digital histopathological whole-slide images，数字化组织病理学全片染色情况显示**
由于数据量大，对千兆像素全切片图像(WSIs)的染色情况分析具有挑战性。在本研究中，我们提出了一种直观的方法来可视化苏木素和伊红(H&E)染色的wsi的颜色风格，该方法可扩展到大型现实世界的队列。为此，在滑动水平上[采用k -均值聚类方法得到具有代表性的颜色光谱](https://github.com/Dilan1020/PyColorPalette)，并将光谱间的成对距离表示为匹配问题。最后，我们使用多维尺度算法(MDS)对WSIs进行二维嵌入，得到适合于可视化的[二维嵌入](%28https://github.%20com/lab-robotics-unipv/mds_experiments)。您可以使用此工具可视化成百上千张图像的染色（即颜色）图案。[【代码入口】](https://github.com/jiaoyiping630/Stain_visualization)
13. **2022年，StainCUT: Stain Normalization with Contrastive Learning，污点归一化与对比学习**
一种基于对比学习的深度学习解决方案，以从一种染色风格转移到另一种染色风格:StainCUT。这种方法不需要选择参考框架，也不需要不同染色的成对图像来学习染色分布之间的映射关系。此外，它不依赖于CycleGAN方法，这使得该方法在内存消耗和运行时间方面非常高效。[【代码入口】](https://github.com/abhishekvahadane/CodeRelease_ColorNormalization)
---
## 3. 图像质量评估
### 感知相似度
[【代码入口】](https://github.com/richzhang/PerceptualSimilarity)
## HistoQC
HistoQC 是用于数字病理切片的开源质量控制工具，[【代码入口】](https://github.com/choosehappy/HistoQC)
“HistoQC：用于数字病理学幻灯片的开源质量控制工具”，Janowczyk A.，Zuo R.，Gilmore H.，Feldman M.，Madabhushi A.，JCO临床癌症信息学，2019

“肾脏全玻片图像活检的计算机化定量质量控制工具的评估”，Chen Y.，Zee J.，Smith A.，Jayapandian C.，Hodgin J.，Howell D.，Palmer M.，Thomas D.，Cassol C.，Farris A.，Perkinson K.，Madabhushi A.，Barisoni L.，Janowczyk A.，病理学杂志，2020年
## SSIM
[【代码入口】](https://github.com/w13b3/SSIM-py)
## FID score
FID是两个图像数据集之间相似性的度量。它被证明与人类对视觉质量的判断密切相关，并且最常用于评估生成对抗网络样本的质量。FID是通过计算两个高斯拟合到Inception网络的特征表示之间的弗雷谢距离来计算的。[【代码入口】](https://github.com/mseitzer/pytorch-fid)

## 4.其它
染色分离和归一化
[【matlab代码入口】](https://github.com/mitkovetta/staining-normalization)[【python代码入口】](https://github.com/mitkovetta/staining-normalization)
最初发表于2013年有丝分裂检测算法评估挑战网站（http://http://amida13.isi.uu.nl）， 一种用于归一化组织学载玻片以进行定量分析的方法，M Macenko，M Niethammer，JS Marron，D Borland，JT Woosley，G Xiaojun，C Schmitt，NE Thomas，IEEE ISBI，2009。dx.doi.org/10.1109/ISBI.2009.5193250

### POT： Python Optimal Transport
信号，图像处理和机器学习的最佳传输相关的优化问题提供了几个求解器python库。[【代码入口】](https://github.com/PythonOT/POT)

---
持续更新整理中……
