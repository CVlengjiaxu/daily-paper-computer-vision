# daily-paper-computer-vision

## 2018-9-10:

### Semi-convolutional Operators for Instance Segmentation (ECCV2018)
Abstract：Object detection and instance segmentation are dominated by region-based methods such as Mask RCNN. However, there is a growing interest in reducing these problems to pixel labeling tasks, as the latter could be more efficient, could be integrated seamlessly in image-to-image network architectures as used in many other tasks, and could be more accurate for objects that are not well approximated by bounding boxes. In this paper we show theoretically and empirically that constructing dense pixel embeddings that can separate object instances cannot be easily achieved using convolutional operators. At the same time, we show that simple modifications, which we call semi-convolutional, have a much better chance of succeeding at this task. We use the latter to show a connection to Hough voting as well as to a variant of the bilateral kernel that is spatially steered by a convolutional network. We demonstrate that these operators can also be used to improve approaches such as Mask RCNN, demonstrating better segmentation of complex biological shapes and PASCAL VOC categories than achievable by Mask RCNN alone.

摘要：目标检测（Object detection）和实例分割（instance segmentation）由基于区域的方法（例如Mask RCNN）主导。然而，人们越来越关注将这些问题减少到像素标记任务，因为后者可以更高效，可以在许多其他任务中使用的图像到图像（image-to-image）网络架构中无缝集成，并且对于不能由边界框近似的目标更加准确。在本文中，我们从理论和经验上表明，使用卷积算子不能轻易地实现构建可以分离对象实例的 dense pixel embeddings 。同时，我们表明简单的修改，我们称之为 semi-convolutional，其在这项任务中有更好的表现。我们证明了这些算子也可用于改进Mask RCNN等方法，展示了比单独使用Mask RCNN可实现的复杂生物形状和PASCAL VOC类别更好的分割。

总结:卷积神经网络是局部的和平移不变的,因此当图像中存在一个object的多个复制时,他将会把他们着同样的颜色,因此不适合实例分割(需要考虑全局信息来给不同object着色).本文提出一种semi-convolutional operator(考虑卷积特征+位置信息),并将其成功应用于Mask RCNN:1.首先得到检测区域 2.用FCN生成分割图(前景概率图),取其中为前景概率最大的像素点最为起点,然后选出与其类似的像素,重新给像素赋予前景概率.  (Mask RCNN的分割为什么是基于proposal,而不是基于全局进行分割?)

### Self-produced Guidance for Weakly-supervised Object Localization
Abstract. Weakly supervised methods usually generate localization results based on attention maps produced by classification networks. However, the attention maps exhibit the most discriminative parts of the object which are small and sparse. We propose to generate Self-produced Guidance (SPG) masks which separate the foreground i.e., the object
of interest, from the background to provide the classification networks
with spatial correlation information of pixels. A stagewise approach is
proposed to incorporate high confident object regions to learn the SPG
masks. The high confident regions within attention maps are utilized
to progressively learn the SPG masks. The masks are then used as an
auxiliary pixel-level supervision to facilitate the training of classification
networks. Extensive experiments on ILSVRC demonstrate that SPG is
effective in producing high-quality object localizations maps. Particu-
larly, the proposed SPG achieves the Top-1 localization error rate of
43.83% on the ILSVRC validation set, which is a new state-of-the-art
error rate.


摘要:弱监督方法通常基于分类网络产生的注意力图（attention maps）生成定位结果。然而，注意力图表现出对象的最具辨别力的部分，这些部分是小的和稀疏的。我们提出生成自生导引（generate Self-produced Guidance ，SPG）掩模，其将前景，感兴趣对象与背景分离，以向分类网络提供像素的空间相关信息。提出了一种分阶段（stagewise）方法，以结合高置性对象区域来学习SPG掩模。注意力图中的高置信区域用于逐步学习SPG掩模。然后将掩模用作辅助像素级监督，以便于分类网络的训练。对ILSVRC的广泛实验表明，SPG可有效地生成高质量的对象定位图。特别是，提出的SPG在ILSVRC验证集上实现了43.83％的Top-1定位错误率，这是一种新的SOTA错误率

总结:将后一层生成的注意力图作为上一层注意力图生成的GT,越到前面层定位的注意力区域更准确(浅层包含丰富的位置信息)

### Modeling Visual Context is Key to Augmenting Object Detection Datasets
Abstract：Performing data augmentation for learning deep neural networks is well known to be important for training visual recognition systems. By artificially increasing the number of training examples, it helps reducing overfitting and improves generalization. For object detection, classical approaches for data augmentation consist of generating images obtained by basic geometrical transformations and color changes of original training images. In this work, we go one step further and leverage segmentation annotations to increase the number of object instances present on training data. For this approach to be successful, we show that modeling appropriately the visual context surrounding objects is crucial to place them in the right environment. Otherwise, we show that the previous strategy actually hurts. With our context model, we achieve significant mean average precision improvements when few labeled examples are available on the VOC'12 benchmark.

Abstract：众所周知，用于深度神经网络的数据增广（data augmentation）对于训练视觉识别系统是十分重要的。通过人为增加训练样本的数量，它有助于减少过度拟合并改善泛化。对于物体检测（object detection），用于数据增强的经典方法包括生成通过基本几何变换和原始训练图像的颜色变化获得的图像。在这项工作中，我们更进一步，利用 segmentation annotations 来增加训练数据上存在的对象实例的数量。为了使这种方法获得成功，我们证明，适当地建模对象周围的视觉上下文（ visual context ）对于将它们放置在正确的环境中至关重要。否则，我们会发现之前的策略确实会受到伤害。通过我们的上下文（context）模型，当VOC'12基准测试中很少有标记示例可用时，我们实现了显著的平均精度改进。

总结：基于可视化上下文建模的数据增强！通过学习的上下文来生成新的数据，增加训练实例的数量。

## 2018-9-10:

### context refinement  for object detection

Abstract. Current two-stage object detectors, which consists of a re- gion proposal stage and a refinement stage, may produce unreliable re- sults due to ill-localized proposed regions. To address this problem, we propose a context refinement algorithm that explores rich contextual in- formation to better refine each proposed region. In particular, we first identify neighboring regions that may contain useful contexts and then perform refinement based on the extracted and unified contextual in- formation. In practice, our method effectively improves the quality of the final detection results as well as region proposals. Empirical studies show that context refinement yields substantial and consistent improve- ments over different baseline detectors. Moreover, the proposed algorithm brings around 3% performance gain on PASCAL VOC benchmark and around 6% gain on MS COCO benchmark respectively.

摘要：当下的二阶段目标检测器主要由一个候选框生成阶段和一个候选框改良阶段组成。对于那些定位失准的候选框，这样的检测器很可能产生不可靠的检测结果。我们研究了这个问题，并尝试使用由附近的候选框所带来的丰富上下文信息来解决它。具体来说，对于每一个候选框，我们首先找到它附近具有有益上下文信息的其他候选框，然后基于从其他候选框提取和整合的上下文信息来对该候选框进行考虑上下文关系的改良。在实际应用中，我们的方法能有效提高最后检测结果的质量，同时也能提高候选框本身的质量。实验数据证明了我们提出的方法能针对不同基线检测器和不同基准测试集带来稳定的提升。详细地说，我们的方法在PASCAL VOC和MS COCO两个基准数据集上为基线检测器分别带来了3%和6%的提升。

总结：利用local context，方法很简单，但是写的好~~ so accepted


