---
title: Paper Review. Learning from Noisy Anchors for One-stage Object Detection@CVPR' 2020
author: JooChan Park
date: 2021-06-02 13:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, CV]
math: true
pin: true
---

- [Paper link](https://openaccess.thecvf.com/content_CVPR_2020/html/Li_Learning_From_Noisy_Anchors_for_One-Stage_Object_Detection_CVPR_2020_paper.html)

## **Abstract**
- 문제점
    - IoU(Intersection over Union)을 통해 positive와 negative anchor를 나누게 되면 noise anchor가 발생해 학습이 잘 되지 않는 문제가 발생함

- 해결책
    - Anchor의 좋고(positive) 나쁨(negative)을 2분할하여 표현하지 않고 동적으로 연속적인 값으로 표현함
    - 지난번 포스팅했던 DAL[1] 방법론과 유사하게 classification branch와 regression branch를 사용하여 좋은 anchor를 분류하는 cleanliness score를 제안함

- 추가적으로 발생하는 계산량은 거의 없으며, COCO데이터셋에서 성능을 2%이상 증가시킴

## **Introduction**

### Positive/Negative Anchor 선택의 중요성 및 문제점

<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide1.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide2.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide3.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide4.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide5.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide6.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide7.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide8.PNG' width='800'>

### 제안하는 Positive/Negative Anchor 선택 방법
- 문제점
    - IoU(Intersection over Union)을 통한 positive/negative anchor 선택으로 학습이 잘되지 않아 classification과 regression간의 불일치 문제 발생

- 제안하는 해결 방법 1
    - Anchor를 positive/negative로 discrete하게 나누지 말고 continuous한 값으로 표현하자

- 제안하는 해결 방법 2
    - Classification branch와 regression branch의 결과값을 사용하여 좋은(positive) anchor를 선택해보자

<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide9.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide10.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide11.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide12.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide13.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide14.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide15.PNG' width='800'>

## **Proposed Method**

### Soft Label
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide16.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide17.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide18.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide19.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide20.PNG' width='800'>

### Sample Re-Weighting
- One-stage detector는 two-stage detector와 다르게 RPN이 존재하지 않기 때문에 negative proposal이 매우 많으며, positive proposal은 적음
- 이 문제를 완화하기 위해 focal loss가 존재하지만, 레이블이 노이즈가 있는 즉 anchor의 좋고 나쁨이 잘못 판별된 위치의 proposal은 학습하는데 방해가 됨
- 그러므로 cleanliness score를 활용한 re-weight sample방법을 제안함

<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide21.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide22.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide23.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide24.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide25.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide26.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide27.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide28.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide29.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide30.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide31.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide32.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide33.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide34.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide35.PNG' width='800'>

## **Experiments**

### Experimental Setup
- Dataset
    - 학습용 : COCO trainval135k set
    - 테스트용 : COCO test-dev2017

- Detectors
    - 주로 사용한 모델 : RetinaNet
    - 벡본 : ResNet-50, ResNet-101, ResNeXt-101 32x8d

- Implementation details
    - GPUs : 4
    - Batch size : 8 (2 images per GPU)
    - Optimizer : SGD
    - Input image size : 800 x 800
    - Augmentation : horizontal flip
    - Multi-scale training 사용 {640, 672, 704, 736, 768, 800} 
    - Multi-scale testing 사용 {400, 500, 600, 700, 900, 1000, 1100, 1200}

### Ablation Study

<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide36.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide37.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide38.PNG' width='800'>

### Main Results

<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide39.PNG' width='800'>

### Discussions

<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide40.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide41.PNG' width='800'>
<img src='\assets\papers\Learning from Noisy Anchors for One-stage Object Detection\slide42.PNG' width='800'>

## **Conclusions & Reviews**
- IoU(Intersection over Union)을 통해 positive와 negative anchor를 나누게 되면 noise anchor가 발생해 학습이 잘 되지 않기 때문에 classification branch와 regression branch를 사용하여 좋은 anchor를 분류하는 cleanliness score를 제안함

- Anchor의 좋고(positive) 나쁨(negative)을 2분할하여 표현하지 않고 동적으로 연속적인 값 soft label로 표현하여 anchor의 표현을 다양하게(풍부하게) 해주는 방법이 재밌었음

- Anchor를 생성하는 것도 중요하지만 학습하기에 좋은 anchor인지 안 좋은 anchor인지 판별하는 것 또한 매우 중요함

## **Reference**
1.  Ming, Qi, et al. "Dynamic Anchor Learning for Arbitrary-Oriented Object Detection." arXiv preprint arXiv:2012.04150 (2020).
