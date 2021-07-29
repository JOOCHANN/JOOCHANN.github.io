---
title: Paper Review. EfficientDet - Scalable and Efficient Object Detection@CVPR' 2020
author: JooChan Park
date: 2020-01-08 18:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, CV]
math: true
pin: False
---

- [Paper link](https://openaccess.thecvf.com/content_CVPR_2020/html/Tan_EfficientDet_Scalable_and_Efficient_Object_Detection_CVPR_2020_paper.html)


## **Abstract**
- Feature Pyramid Networ(FPN)의 구조 Weighted bi-directional FPN(BiFPN)을 제안함

- EfficientNet에서 제안한 Compound Scaling기법을 Object Detection에 적용함

- One-stage Detection

## **Proposed Methods**

### BiFPN
- One-Stage Detector의 여러 대표 모델인 SSD, RetinaNet, M2Det의 FPN들은 서로 다른 input feature들을 합칠 때 단순히 resize후 더해주는 방식을 지적함

- 서로 다른 input feature들은 해상도가 다르기 때문에 output feature에 기여하는 정도를 다르게 가져야함을 주장함

- 간단하지만 효과적인 weighted bi-directional FPN 구조를 제안함

- BiFPN구조는 서로 다른 input feature들의 중요성을 학습을 통해 배울 수 있고, 성능을 많이 향상 시킬 수 있음

<img src='\assets\papers\EfficientDet\1.PNG' width='800'>
<img src='\assets\papers\EfficientDet\2.PNG' width='800'>
<img src='\assets\papers\EfficientDet\3.PNG' width='800'>
<img src='\assets\papers\EfficientDet\4.PNG' width='800'>

### EfficientDet
<img src='\assets\papers\EfficientDet\5.PNG' width='800'>
<img src='\assets\papers\EfficientDet\6.PNG' width='800'>
<img src='\assets\papers\EfficientDet\7.PNG' width='800'>
<img src='\assets\papers\EfficientDet\8.PNG' width='800'>
<img src='\assets\papers\EfficientDet\9.PNG' width='800'>

### Focal Loss
- Cross Entropy Loss를 조금 수정함

- 잘 분류되는 이미지들에 대해서는 작은 가중치를 부여하는 반면 분류하기 어려운 일부 이미지에는 큰 가중치를 부여함

- 쉽게 분류되는 대부분의 negative 샘플들에 의해서 학습이 압도 되는 문제를 해결 함

- One-Stage 방식에서도 Two-Stage 만큼의 성능을 낼 수 있음

<img src='\assets\papers\EfficientDet\10.PNG' width='800'>
<img src='\assets\papers\EfficientDet\11.PNG' width='800'>

## **Experiments**
<img src='\assets\papers\EfficientDet\12.PNG' width='800'>
<img src='\assets\papers\EfficientDet\13.PNG' width='800'>
<img src='\assets\papers\EfficientDet\14.PNG' width='800'>
<img src='\assets\papers\EfficientDet\15.PNG' width='800'>
<img src='\assets\papers\EfficientDet\16.PNG' width='800'>

## **Conclusions & Reviews**
- EfficientNet을 활용한 Object Detection이였으며, 앞으로 Segmentation에도 EfficientNet을 활용한 논문이 나올 것 같음


## **Reference**
