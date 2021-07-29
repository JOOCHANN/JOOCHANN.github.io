---
title: Paper Review. Align Deep Features for Oriented Object Detection@IEEE Transactions on Geoscience and Remote Sensing' 2021
author: JooChan Park
date: 2021-04-14 13:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, Oriented Object Detection, CV]
math: true
pin: true
---

- [Paper link](https://ieeexplore.ieee.org/abstract/document/9377550?casa_token=ftqghqE0R94AAAAA:IrBS8DpsKG3WrrOyChjwLlgU_T7Tfo2OnmNiBv1cpI9SrNL_1gs9GVZbIW82mawhZ7-FTWov0cc)

## **Abstract**
- 기존 방법들은 scale, angle, aspect ratio를 사용하여 heuristic하게 정의된 anchor에 의존함

- 회전된 Anchor box와 회전되지 않은(axis-aligned) convolution사이의 misalignment로 인해 classification과 localization 정확도 간에 불일치가 존재함

- Single-shot alignment Network(S^2A-Net)은 두개의 모듈로 이루어져 있음.
    - Feature Alignment Module(FAM) : 고품질 anchor를 생성하고, alignment convolution을 통해 anchor 위치에 맞는 convolution을 수행함
    - Oriented Detection Module(ODM) : Active Rotating Filters(ARF)를 사용해 방향 정보를 인코딩하여 orientation-sensitive feature를 제공함으로써 classification과 localization 정확도 간의 불일치를 어느정도 해결함

- DOTA 데이터 셋에서 SOTA를 달성함

## **Introduction**

<img src='\assets\papers\Align Deep Features for Oriented Object Detection\1.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\2.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\3.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\4.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\5.PNG' width='800'>

- Anchor box와 object간의 misalignment를 해결하기 위해 논문에서는 Single-shot alignment Network(S^2A-Net)을 제안함.

- Feature Alignment Module(FAM)
    - 다른 방법론들과 다르게 하나의 horizontal anchor를 갖음.
    - Anchor Refinement Network (ARN)에서 고품질의 회전된 anchor를 생성함.
    - Alignment convolution을 통해 anchor 위치에 맞는 convolution을 수행함.

- Oriented Detection Module(ODM)
    - Active Rotating Filters(ARF)를 사용해 방향 정보를 인코딩하여 orientation-sensitive feature를 제공함으로써 classification과 localization 정확도 간의 불일치를 어느정도 해결함.

## **Proposed Method**

### Model Architecture - FPN
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\6.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\7.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\8.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\9.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\10.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\11.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\12.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\13.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\14.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\15.PNG' width='800'>

### Model Architecture - FAM
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\16.PNG' width='800'>

#### Anchor Refinement Network
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\17.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\18.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\19.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\20.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\21.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\22.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\23.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\24.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\25.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\26.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\27.PNG' width='800'>

#### Alignment Convolution Layer
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\28.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\29.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\30.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\31.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\32.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\33.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\34.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\35.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\36.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\37.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\38.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\39.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\40.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\41.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\42.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\43.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\44.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\45.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\46.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\47.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\48.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\49.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\50.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\51.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\52.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\53.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\54.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\55.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\56.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\57.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\58.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\59.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\60.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\61.PNG' width='800'>

### Model Architecture - ODM
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\62.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\63.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\64.PNG' width='800'>

#### Active Rotating Filters
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\65.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\66.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\67.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\68.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\69.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\70.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\71.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\72.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\73.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\74.PNG' width='800'>

### Model Architecture - Summary
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\75.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\76.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\77.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\78.PNG' width='800'>

### Loss Function
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\79.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\80.PNG' width='800'>

## **Experiments**

- Dataset
    - DOTA
        - 크기 범위 : 800 x 800 ~ 4000 x 4000
        - 이미지 수 : 2806
        - Augmentation : 좌,우,상,하 flip, multi scale training, multi scale test

    - HRSC2016
        - 크기 범위 : 300 x 300 ~ 1500 x 900
        - 이미지 수 : 617
        - Augmentation : 좌,우 flip

<img src='\assets\papers\Align Deep Features for Oriented Object Detection\81.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\82.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\83.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\84.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\85.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\86.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\87.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\88.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\89.PNG' width='800'>
<img src='\assets\papers\Align Deep Features for Oriented Object Detection\90.PNG' width='800'>

## **Conclusions & Reviews**
- Feature Alignment Module과 Oriented Detection Module이 포함된 Single-Shot Alignment Network을 제안하며 속도와 정확도 모두 챙김

- Predict box 정보를 Anchor box에 넣어서 학습 가능한 refine anchor를 만드는 방법이 좋았음

- Deformable convolution을 쓸 때, offset field를 refine anchor를 기반으로 가져오기 때문에 효과가 있었음

- 모델이 갈수록 어려워지는 것 같고, 논문에서는 아주 간략하게 설명하기 때문에 전반적인 기초 지식이 없으면 이해하기 힘듬

- 코드를 뜯어보며 살펴보니 모델 구조를 명확히 이해할 수 있었고, Loss부분도 자세하게 뜯어볼 계획임

## **Reference**
1.  Zhou, Yanzhao, et al. "Oriented response networks." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2017.
