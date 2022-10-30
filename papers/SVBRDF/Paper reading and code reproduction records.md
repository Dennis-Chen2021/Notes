# Paper reading and code reproduction records



## 1.`Deep Inverse Rendering for High-resolution SVBRDF Estimation from an Arbitrary Number of Images`[ACM SIGGRAPH 2019 Q1]

### 1.1 目的动机

#### 1.1.1 现阶段缺点:

​		**传统纹理材质建模**:主要对目标材质样本进行**大量图像采集**，并进行数据驱动建模。这样就要求这大量的图像，要包含**不同光照**、**视角**等等(即:图片要与纹理模型的本征自由度有关)，大量图片才能保证不出现二义性。

​		**深度学习的方法：**<u>通过神经网络从单张输入图片来预测纹理材质的方</u>法。深度学习可以充分利用训练数据中真实世界的材质属性的分布信息，即使存在二义性，也可以根据先验知识给出“合理”预测。这里的“合理”表示预测的纹理材质看起来和实际测量目标的纹理材质非常相似，并且不存在明显的瑕疵(artifacts)，但是，这种预测的结果不一定能精确反应实际测量目标的材质属性。【单张图片并不一定能反映材质的全部属性，例如:在不同光照条件下，神经网络通过预测的纹理材质就可能存在偏差】<u>当前基于深度学习的方法，尚不能利用更多图像信息来进一步改进这一“合理”的预测结果。</u>



### 1.2  主要思想



### 1.3  代码复现

#### 1.3.1 输入&&输出&&数据集

- 输入：
- 输出:
- 数据集：



## 2.`Flexible SVBRDF Capture with a Multi-Image Deep Network`




