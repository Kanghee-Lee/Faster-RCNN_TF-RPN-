# Faster-RCNN_TF-RPN-
Tensorflow re-implementation of RPN in Faster R-CNN: [Towards Real-Time ObjectDetection with Region Proposal Networks.](https://arxiv.org/abs/1506.01497)

## Introduction
In Fast R-CNN, region proposal is proceeded with selective search algorithm which is computed outside the CNN module.

So generating RoI(region of interest) was the bottleneck.


By sharing conv feature map in RPN(region proposal network), we can generate RoI from conv feature map.

It is computed by gpu, while generation of RoI in Fast R-CNN is computed by cpu.

## Architecture
![Architecture](https://user-images.githubusercontent.com/45263010/73349987-8b3e4980-42cf-11ea-821e-98f5437698b7.PNG)

Adapted until pool-3 layer of VGG as backbone, (32, 64, 128) for scale and (0.5, 1.0, 2.0) for ratio. 

Both scale and ratio is corresponds to the scale and ration of the anchor box projected onto the original image.
