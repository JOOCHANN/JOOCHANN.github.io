---
title: Paper Review. Deformable Convolutional Networks@ICCV' 2017
author: JooChan Park
date: 2020-04-29 18:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, CV]
math: true
pin: False
---

- [Paper link](https://openaccess.thecvf.com/content_iccv_2017/html/Dai_Deformable_Convolutional_Networks_ICCV_2017_paper.html)

## **Abstract**
- 기존 CNN에서 사용하는 conv, pooling이 기하학적으로 일정한 패턴을 가정하고 있기 때문에 복잡한 transformation에 유연하게 대처하기 어려움

- 기존에는 weight을 구하는 방법에 초첨을 맞췄다면, 이 논문은 어떤 데이터를 뽑을 것인지에 초점을 둠

- Convolution -> Convolution + learnable offset

- RoI pooling -> RoI pooling + learnable offset

## **Introduction**
<img src='\assets\papers\Deformable Convolutional Networks\1.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\2.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\3.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\4.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\5.PNG' width='800'>


## **Proposed Method**
### Deformable Convolution
<img src='\assets\papers\Deformable Convolutional Networks\6.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\7.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\8.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\9.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\10.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\11.PNG' width='800'>

### Deformable RoI Pooling
<img src='\assets\papers\Deformable Convolutional Networks\12.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\13.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\14.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\15.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\16.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\17.PNG' width='800'>

### Understanding Deformable ConvNets
<img src='\assets\papers\Deformable Convolutional Networks\18.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\19.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\20.PNG' width='800'>


## **Experiments**
<img src='\assets\papers\Deformable Convolutional Networks\21.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\22.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\23.PNG' width='800'>
<img src='\assets\papers\Deformable Convolutional Networks\24.PNG' width='800'>


## **Conclusions & Reviews**
- 데이터의 특징을 필터를 통해 찾는 것이 아니라 입력 데이터에서 offset을 통해 직접 찾으려 해서 참신함

- Deformable convolution과 deformable RoI pooling을 사용했을 때 의미 분석을 그림으로 보여주어 직관적으로 왜 좋아졌는지 느낄 수 있었음

- 모든 물체가 정사각형으로 이루어져 있지 않기 때문에 정사각형의 필터를 가지고 convolution을 하는 것은 문제가 될 수 있으며, 이 문제를 해결하는 하나의 방향성을 제시해 준 것 같음


## **Reference**
