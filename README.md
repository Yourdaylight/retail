# Water Quility Evaluation
基于自动机器学习的水色图像水质评价

## 一、背景介绍
   从事渔业生产有经验的从业者可通过观察水色变化调控水质，以维持养殖水体生态系统中浮游植物、微生物类、浮游动物等合理的动态平衡。由于这些多是通过经验和肉眼观察进行判断，存在主观性引起的观察性偏倚，使观察结果的可比性、可重复性降低，不易推广应用。当前，数字图像处理技术为计算机监控技术在水产养殖业的应用提供更大的空间。在水质在线监测方面，数字图像处理技术是基于计算机视觉，以专家经验为基础，对池塘水色进行优劣分级，达到对池塘水色的准确快速判别。
  
## 二、数据说明
### 1、原始数据
  共计五类水色图片，命名规则为：水色类别_编号。

  图片数量：203张图片(每张图片约为400万像素)
  图片类别：5类图片
  
### 2、处理后的数据
 通过求每张图片的R、G、B通道的一二三阶矩阵作为每张图片的特征
 生成203*9的DataFrame作为训练数据data，保存为data.json    
 同时根据命图片的命名，获取图片的类别作为数据的标签 label,保存为label.json
 
## 三、数据建模与模型评估
将测试集与训练集按2:8进行划分、分别代入决策树、K近邻、朴素贝叶斯、神经网络与支持向量机等分类模型中进行训练，并通过分类的准确率与混淆矩阵对模型进行评估。
在训练模型时，为了找到最好的参数，我们通过sklearn中的GridSearchCV对模型的参数进行网格搜索，使得模型的效果尽可能地好。



