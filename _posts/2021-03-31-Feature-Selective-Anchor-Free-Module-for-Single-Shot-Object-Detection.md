---
title: Paper Review. Feature Selective Anchor-Free Module for Single-Shot Object Detection@CVPR' 2019
author: JooChan Park
date: 2021-03-31 13:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, Anchor Free, CV]
math: true
pin: False
---

- [Paper link](https://openaccess.thecvf.com/content_CVPR_2019/html/Zhu_Feature_Selective_Anchor-Free_Module_for_Single-Shot_Object_Detection_CVPR_2019_paper.html)

## **Abstract**
- Anchor 기반의 detecting 방식에는 두 가지의 한계점이 존재
    1. heuristic-guide를 통한 feature selection
    2. overlap-based anchor sampling

- 모델의 전체적인 구조는 FPN을 통과한 Feature map에 기존 방식인 anchor-based branch와 논문에서 제안하는 anchor-free branch을 통해 객체를 검출

- Anchor-free branch에서 online feature selection을 하는 FSAF(Feature Selection Anchor Free)방식을 제안함

- FSAF 방식은 가볍고 빠르며 플러그인 시키기 쉬움

<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\img1.PNG' width='800'>
_Fig1. 제안하는 방법 FSAF는 작은 오브젝트를 잘 찾을 수 있음_


## **Introduction**
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\1.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\2.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\3.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\4.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\5.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\6.PNG' width='800'>

## **Proposed Method**

### Network Architecture
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\7.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\8.PNG' width='800'>

### Ground-truth and Loss
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\9.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\10.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\11.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\12.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\13.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\14.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\15.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\16.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\17.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\18.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\19.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\20.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\21.PNG' width='800'>

### Online Feature Selection
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\22.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\23.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\24.PNG' width='800'>

## **Experiments**
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\25.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\26.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\27.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\28.PNG' width='800'>
<img src='\assets\papers\Feature Selective Anchor-Free Module for Single-Shot Object Detection\29.PNG' width='800'>

## **Conclusions & Reviews**
- 가볍고 빠르며 어디에든 추가하기 쉬운 FSAF 모듈을 제안함

- Anchor-based 방법에서는 작은 오브젝트는 low level의 feature pyramid map을 사용하고, 큰 오브젝트는 high level의 feature map을 사용하여 detection을 하며 이는 성능적으로 한계가 있음

- 논문에서는 anchor-free branch를 추가함으로써 feature map을 동적으로 선택하므로 오브젝트를 더 잘 찾을 수 있었음

- 작은 오브젝트는 low level의 feature pyramid map을 사용하고, 큰 오브젝트는 high level의 feature map을 사용하는 이유는 IoU를 통해 positive anchor를 선택하기 때문이며, 결국 IoU를 통해 앵커를 선택하는 방법은 좋지 않음


## **Reference**
