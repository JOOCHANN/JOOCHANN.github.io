---
title: Paper Review. Gliding vertex on the horizontal bounding box for multi-oriented object@IEEE transactions on pattern analysis and machine intelligence' 2020
author: JooChan Park
date: 2020-06-02 18:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, Oriented Object Detection, CV]
math: true
pin: False
---

- [Paper link](https://ieeexplore.ieee.org/abstract/document/9001201?casa_token=R_LrtCbzL4QAAAAA:3YPWwU6yo4ysQverP0MVY6M7ogWpzNIvCLQldEhaIJchm9r5DNjzHs3OiNYasEkLeYy4jqKn29s)

## **Abstract**
- Multi-oriented object를 detection하기 간단하지만 효과적인 프레임워크

- Oriented object의 네 꼭지점을 직접적으로 예측하는 것이 아닌, horizontal한 박스를 가지고 gliding offset을 예측하여 oriented object의 꼭지점을 예측함

- Oriented object와 horizontal한 박스 사이의 면적 비율을 기반으로 obliquity factor를 측정하여 어떤 박스를 선택할지 결정함

<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\1.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\2.PNG' width='800'>

## **Introduction**
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\3.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\4.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\5.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\6.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\7.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\8.PNG' width='800'>

## **Proposed Method**

### Multi-Oriented Object Representation
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\9.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\10.PNG' width='800'>

### Network Architecture
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\11.PNG' width='800'>

### Training Objective
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\12.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\13.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\14.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\15.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\16.PNG' width='800'>

## **Experiments**
- Dataset
    - DOTA 
        - A large-scale and challenging dataset for object detection in aerial images with quadrangle annotations
    - HRSC2016
        - Ship detection in aerial images
    - MSRA-TD500
        - Detecting long and oriented texts
    - RCTW-17
        - Detecting long and oriented texts
    - MW-18Mar
        - Multi-target horizontal pedestrian tracking dataset

<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\17.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\18.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\19.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\20.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\21.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\22.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\23.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\24.PNG' width='800'>
<img src='\assets\papers\Gliding vertex on the horizontal bounding box for multi-oriented object detection\25.PNG' width='800'>

## **Conclusions & Reviews**
- Multi-oriented object를 detection하기 간단하지만 효과적인 프레임워크

- RPN에서 Anchor를 찾을 때 각도를 고려하지 않았기 때문에 다른 기존 2-stage 방법들보다 속도가 빠름

- 회전된 객체 탐지 다양한 데이터셋에서 당시 SOTA를 찍음으로써, 자신들이 제안하는 (회전된 객체를 바라보는 representation)방법이 회전된 객체를 찾는 일반적인 태스크에 효과적이라는 것을 보여줌

- 회전된 객체를 바라보는 일반적인 시선을 다른 시선으로 바라본 것이 새로웠음


## **Reference**
