---
title: Paper Review. Faster R-CNN Towards Real-Time Object Detection with Region Proposal Networks@NIPS' 2015
author: JooChan Park
date: 2020-02-18 18:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, CV]
math: true
pin: False
---

- [Paper link](https://proceedings.neurips.cc/paper/2015/file/14bfa6bb14875e45bba028a21ed38046-Paper.pdf)


## **R-CNN**
- 최초로 object detection task에 CNN을 사용하여 정확도와 속도를 획기적으로 향상시킴

### R-CNN의 구조
<img src='\assets\papers\Faster R-CNN\1.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\2.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\3.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\4.PNG' width='800'>

### R-CNN 학습방법
<img src='\assets\papers\Faster R-CNN\5.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\6.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\7.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\8.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\9.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\10.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\11.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\12.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\13.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\14.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\15.PNG' width='800'>

### R-CNN Experiments
<img src='\assets\papers\Faster R-CNN\16.PNG' width='800'>

### R-CNN Conclusions & Reviews
- 학습이 일어나는 부분
    - 이미지 넷으로 이미 학습된 모델을 가져와 fine tuning하는 부분
    - SVM classifier를 학습시키는 부분
    - Bounding box regression하는 부분

- 학습시간이 오래 걸림
    - Selective search에서 뽑아낸 2000개의 영역 이미지들에 대해서 모두 CNN모델을 통과하므로 오래걸림
    - Selective search는 CPU를 사용하는 알고리즘

- AlexNet을 그대로 사용하기 위해 이미지를 224 x 224 크기로 강제로 warping시켰기 때문에 이미지 변형으로 인한 성능 손실

- CNN, SVM, Bounding box regression 총 세가지 모델을 필요로 하는 복잡한 구조

- Multi-Stage Training을 수행, SVM에서 학습한 결과가 CNN을 업데이트 시키지 못함

- R-CNN은 최초로 object detection에 deep learning 방법인 CNN을 적용시킴


## **Fast R-CNN**
- CNN fine tuning, bounding box regression, classification을 모두 하나의 네트워크에서 학습시키는 end to end 기법

- R-CNN의 단점을 보완하기 위해 나온 논문

- 핵심 아이디어는 RoI pooling

### Fast R-CNN의 구조
<img src='\assets\papers\Faster R-CNN\17.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\18.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\19.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\20.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\21.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\22.PNG' width='800'>

### Fast R-CNN RoI Pooling
<img src='\assets\papers\Faster R-CNN\23.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\24.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\25.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\26.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\27.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\28.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\29.PNG' width='800'>

### Fast R-CNN Multi Task Loss
<img src='\assets\papers\Faster R-CNN\30.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\31.PNG' width='800'>

### Fast R-CNN Experiments
<img src='\assets\papers\Faster R-CNN\32.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\33.PNG' width='800'>

### R-CNN Conclusions & Reviews
- Fast R-CNN의 training은 end to end로 single stage training을 하지만 region proposal로 selective search를 수행하기 때문에 전체적으로 2-stage detector로 봄

- Fast R-CNN은 R-CNN이나 SPP-net에 비하면 뛰어난 성능을 보이며 학습시간과 테스트 시간이 감소됨, 하지만 region proposal에서 걸리는 시간이 총 2.3초 중 약 2초의 시간이 걸리기 때문에 Bottleneck이 생김


## **Faster R-CNN**
- Region proposal 방법을 GPU를 통한 학습으로 진행하면 확실히 성능이 증가하고 시간이 감소될 것이라고 말함

- Selective search를 사용하여 계산해왔던 region proposal 단계를 neural network 안으로 가져옴

- 핵심 아이디어는 region proposal network(PRN)

### Faster R-CNN 구조
<img src='\assets\papers\Faster R-CNN\34.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\35.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\36.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\37.PNG' width='800'>

### Faster R-CNN Region Proposal Network
<img src='\assets\papers\Faster R-CNN\38.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\39.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\40.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\41.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\42.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\43.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\44.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\45.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\46.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\47.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\48.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\49.PNG' width='800'>

### Faster R-CNN vs Fast R-CNN
<img src='\assets\papers\Faster R-CNN\50.PNG' width='800'>

### 2-Stage 구조 vs 1-Stage 구조
<img src='\assets\papers\Faster R-CNN\51.PNG' width='800'>

### Faster R-CNN Experiments
<img src='\assets\papers\Faster R-CNN\52.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\53.PNG' width='800'>

### Faster R-CNN Conclusions & Reviews
- CNN모델을 통해 Region proposal을 뽑아 빠른 속도를 냄

- RPN이 있어 positive한 anchor와 negative anchor의 비율을 맞춰 줄 수 있다는 점이 좋음

- RPN에서 sliding window를 통해 anchor box를 만들고 난 뒤에 positive와 negative를 판별 할 수 있으므로 결국 RPN도 많은 anchor box를 만들어 주고 GT와 IoU 계산을 다 해주어야 함 (feature map이 클 경우)

- RPN이 학습이 잘 되려면 좋은 anchor box를 만들어 주는 것이 중요하다고 생각됨


## **RoI Align**
- Mask-RCNN 논문에서 제시한 방법

- 기존 RoI pooling의 문제점을 지적하여 나온 RoI align

### RoI Pooling의 문제점
- Fast R-CNN은 object detection을 위한 모델이었기 때문에 RoI pooling에서 아주 정확한 위치 정보를 담는 것이 중요하지 않았음 (Bounding box안에 object이 있으면 됨)

<img src='\assets\papers\Faster R-CNN\54.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\55.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\56.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\57.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\58.PNG' width='800'>

### RoI Align
- RoI align은 Mask R-CNN에서 좋은 성능을 냈음

- 2-Stage object detection에서 RoI pooling보다 RoI align을 썼을 때, 더 자세한 박스 좌표를 얻기 때문에 성능이 더 높음

<img src='\assets\papers\Faster R-CNN\59.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\60.PNG' width='800'>
<img src='\assets\papers\Faster R-CNN\61.PNG' width='800'>


## **Conclusions & Reviews**
- 2-Stage기반의 모델을 자세히 살펴보았으며, RPN이 있으므로 확실히 Object을 잘 찾을 수 있다고 봄

- 여름에 열리는 그랜드 챌린지 2020에는 2-Stage기반의 모델을 선택해 구현해보고 싶음

- 앞으로 2-Stage 기반의 최신 Object Detection 논문을 찾아볼 계획임


## **Reference**
1.  Girshick et al, “Rich feature hierarchies for accurate object detection and semantic segmentation Tech report ”, CVPR, 2014
2.  Uijlings et al, “Selective Search for Object Recognition”, IJCV, 2012
3.  Stanford CS231n, lecture12, p54
4.  https://deepsense.ai/
