---
title: Paper Review. Arbitrary-Oriented Scene Text Detection via Rotation proposals@IEEE Transactions on Multimedia' 2018
author: JooChan Park
date: 2019-11-26 18:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, Oriented Object Detection, CV]
math: true
pin: False
---

- [Paper link](https://ieeexplore.ieee.org/abstract/document/8323240?casa_token=nbnxyMRMpUgAAAAA:zvlxwwUb0TsqpOtKJb5Fw4p-Synz9pT3foz9RiWCFkKTtt6GMoZplHw_Vvwqwdawvih9boY5984)


## **Abstract**
- 이미지에서의 텍스트 감지를 위한 새로운 회전 기반 프레임 워크를 소개

- 텍스트 방향 각도 정보가 포함된 Rotation Region Proposal Networks (RRPN)를 제안함

- Rotation Region-of-Interest (RRoI) pooling layer을 제안함

- Faster-RCNN과 같은 구조로 region proposal-based architecture이다


## **Introduction**
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\1.PNG' width='800'>


## **Proposed Methods**

### Horizontal Region Proposal
- 각 슬라이딩 위치에 k개의 anchor가 존재.

- k anchor에 대해 좌표를 나타내는 box regression(reg) layer
    - 4k outputs (x, y, w, h)

- k anchor에 대해 점수를 나타내는 box-classification (cls) layer
    - 2k scores (object, non object)

- anchor를 정하기 위한 parameter로는 Scale, Ratio를 사용함.
    - Ex) Scale : 1x, 2x, 4x, 1:2, Ratio : 1:1, 2:1

- 기존 수평 anchor box선택 전략은 총 anchor의 수를 낮게 유지할 수 있음.

- 하지만 실제 이미지에서 텍스트를 찾는 경우 박스가 부자연스러운 모양임. 

- 회전된 박스를 찾는 RPN을 제안함.

### Architecture
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\2.PNG' width='800'>

### Rotated Bounding Box Representation
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\3.PNG' width='800'>

### Anchor Strategy
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\4.PNG' width='800'>


### Learning of Rotated Proposal
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\5.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\6.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\7.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\8.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\9.PNG' width='800'>

### Skew IoU Computation
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\10.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\11.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\12.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\13.PNG' width='800'>

### RRoI Pooling Layer
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\14.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\15.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\16.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\17.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\18.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\19.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\20.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\21.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\22.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\23.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\24.PNG' width='800'>

## **Experiments**
- DataSet : MSRA-TD500, ICDAR2015, ICDAR2013

- Implementation Details
    - Learning rate : 0.001 for first 200,000 iterations, 0.0001 for the next 100,000 iterations
    - Weight decay : 0.0005
    - Momentum : 0.9

<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\25.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\26.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\27.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\28.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\29.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\30.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\31.PNG' width='800'>
<img src='\assets\papers\Arbitrary-Oriented Scene Text Detection via Rotation proposals\32.PNG' width='800'>


## **Conclusions & Reviews**
- 전체적인 구조는 Faster-RCNN과 매우 똑같아서 이해하기가 쉬웠음

- RPN을 만들 때 각도 값 𝜃만 추가해 주면 되는 간단한 문제라고 생각 할 수 있지만, RoI Pooling을 할 때 회전된 박스안에 픽셀 값을 받아오는 작업이 쉽지 않다고 느껴짐


## **Reference**
