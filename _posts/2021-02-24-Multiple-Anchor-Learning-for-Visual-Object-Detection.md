---
title: Paper Review. Multiple Anchor Learning for Visual Object Detection@CVPR' 2020
author: JooChan Park
date: 2021-02-24 13:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, CV]
math: true
pin: False
---

- [Paper link](https://openaccess.thecvf.com/content_CVPR_2020/html/Ke_Multiple_Anchor_Learning_for_Visual_Object_Detection_CVPR_2020_paper.html)

## **Abstract**
- 고정된 앵커 집합에 대하여 classification과 regression은 공동으로 최적화하지 못함

- Anchor bag를 구성하여 객체별 대표적인 anchor를 선택하는 방식인 MAL(Multiple Anchor Learning) 방법을 제안함

- 반복적인 anchor 선택 프로세스를 최적화하기 위해 anchor의 confidence를 낮춤으로 교란(perturbing)하여 가장 좋은 anchor를 선택하도록 함


## **Introduction**
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\1.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\2.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\3.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\4.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\5.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\6.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\7.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\8.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\9.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\10.PNG' width='800'>

## **Proposed Method**
### RetinaNet Revisit
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\11.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\12.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\13.PNG' width='800'>

### Multiple Anchor Learning
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\14.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\15.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\16.PNG' width='800'>

### Selection-Depression Optimization
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\17.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\18.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\19.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\20.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\21.PNG' width='800'>

### Implementation
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\22.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\23.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\24.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\25.PNG' width='800'>

### Optimization Analysis
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\26.PNG' width='800'>


## **Experiments**
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\27.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\28.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\29.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\30.PNG' width='800'>
<img src='\assets\papers\Multiple Anchor Learning for Visual Object Detection\31.PNG' width='800'>


## **Conclusions & Reviews**
- Best anchor를 선택하면서 Classification confidence와 localization을 같이 optimize하기 때문에 객체와 anchor를 매칭하는 것을 학습할 수 있음

- 근본적으로는 IoU를 통해 anchor를 선택하는 것이 좋지 않기 때문에 이러한 방법들이 계속해서 연구되고 있음


## **Reference**
