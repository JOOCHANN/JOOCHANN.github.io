---
title: Paper Review. SlowFast Networks for Video Recognition@ICCV' 2019
author: JooChan Park
date: 2020-07-14 18:00:00 +0800
categories: [Paper Reviews, Activity Recognition]
tags: [Activity Recognition, Object Detection, CV]
math: true
pin: true
---

- [Paper link](https://openaccess.thecvf.com/content_ICCV_2019/html/Feichtenhofer_SlowFast_Networks_for_Video_Recognition_ICCV_2019_paper.html)

## **Abstract**
- AVA Challenge 2019에서 Action recognition 1등

- Video Recognition을 위한 네트워크 구조

- 두개의 pathway가 존재
    - Slow pathway : spatial semantic 정보를 획득
    - Fast pathway : motion at fine temporal resolution 정보를 획득

- 사람의 시각 시스템을 모방하여 모델을 구축함

## **Introduction**
<img src='\assets\papers\SlowFast Networks for Video Recognition\1.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\2.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\3.PNG' width='800'>

### Spatial Structure
<img src='\assets\papers\SlowFast Networks for Video Recognition\4.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\5.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\6.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\7.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\8.PNG' width='800'>

### Temporal Events
<img src='\assets\papers\SlowFast Networks for Video Recognition\9.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\10.PNG' width='800'>

### SlowFast Networks
<img src='\assets\papers\SlowFast Networks for Video Recognition\11.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\12.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\13.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\14.PNG' width='800'>

### Biological Derivation
<img src='\assets\papers\SlowFast Networks for Video Recognition\15.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\16.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\17.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\18.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\19.PNG' width='800'>

## **Proposed Method**

### Slow Pathway
<img src='\assets\papers\SlowFast Networks for Video Recognition\20.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\21.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\22.PNG' width='800'>

### Fast Pathway
<img src='\assets\papers\SlowFast Networks for Video Recognition\23.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\24.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\25.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\26.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\27.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\28.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\29.PNG' width='800'>

### Overall Process
<img src='\assets\papers\SlowFast Networks for Video Recognition\30.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\31.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\32.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\33.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\34.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\35.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\36.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\37.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\38.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\39.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\40.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\41.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\42.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\43.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\44.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\45.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\46.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\47.PNG' width='800'>

## **Experiments**
- Dataset
    - Kinetics-400
        - 306,245 video clips
        - 400 human action classes
    - Kinetics-600
        - 495,547 video clips
        - 600 human action classes
    - Charades
        - 9,848 video clips
        - 157 human action classes
    - AVA dataset
        - 430 video clips
        - 80 human action classes

### Action Classification
<img src='\assets\papers\SlowFast Networks for Video Recognition\48.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\49.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\50.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\51.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\52.PNG' width='800'>

### AVA Action Detection
<img src='\assets\papers\SlowFast Networks for Video Recognition\53.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\54.PNG' width='800'>
<img src='\assets\papers\SlowFast Networks for Video Recognition\55.PNG' width='800'>

## **Conclusions & Reviews**
- 사람의 인지 시스템을 모방해 모델구조를 설계하였기 때문에 왜 이렇게 모델 구조를 만들었는지 이해가 됨

- 사람을 탐지하는 모델(Detectron)의 성능이 90프로가 넘으므로 모델을 그대로 사용하고, 사람의 액션을 예측하는데 초점을 둔 모델(Slowfast)을 만든 것 같음

- AI Grand Challenge 첫번째 Task에서는 단순히 실신한 사람만 찾으면 되므로, 이 모델이 적합하지 않을 수 있음. 하지만, 나중에 복잡한 영상 인식 Task가 진행된다면 사용해 볼 수 있음 (클래스수가 많아지거나, 영상이 길어지는 경우)

## **Reference**
