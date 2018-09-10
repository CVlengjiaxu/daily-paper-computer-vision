# daily-paper-computer-vision

## 2018-9-10:

### Semi-convolutional Operators for Instance Segmentation (ECCV2018)
Abstract：Object detection and instance segmentation are dominated by region-based methods such as Mask RCNN. However, there is a growing interest in reducing these problems to pixel labeling tasks, as the latter could be more efficient, could be integrated seamlessly in image-to-image network architectures as used in many other tasks, and could be more accurate for objects that are not well approximated by bounding boxes. In this paper we show theoretically and empirically that constructing dense pixel embeddings that can separate object instances cannot be easily achieved using convolutional operators. At the same time, we show that simple modifications, which we call semi-convolutional, have a much better chance of succeeding at this task. We use the latter to show a connection to Hough voting as well as to a variant of the bilateral kernel that is spatially steered by a convolutional network. We demonstrate that these operators can also be used to improve approaches such as Mask RCNN, demonstrating better segmentation of complex biological shapes and PASCAL VOC categories than achievable by Mask RCNN alone.

摘要：目标检测（Object detection）和实例分割（instance segmentation）由基于区域的方法（例如Mask RCNN）主导。然而，人们越来越关注将这些问题减少到像素标记任务，因为后者可以更高效，可以在许多其他任务中使用的图像到图像（image-to-image）网络架构中无缝集成，并且对于不能由边界框近似的目标更加准确。在本文中，我们从理论和经验上表明，使用卷积算子不能轻易地实现构建可以分离对象实例的 dense pixel embeddings 。同时，我们表明简单的修改，我们称之为 semi-convolutional，其在这项任务中有更好的表现。我们证明了这些算子也可用于改进Mask RCNN等方法，展示了比单独使用Mask RCNN可实现的复杂生物形状和PASCAL VOC类别更好的分割。

创新点总结:

