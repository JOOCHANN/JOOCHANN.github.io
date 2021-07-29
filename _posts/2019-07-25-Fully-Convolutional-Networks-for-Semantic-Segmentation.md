---
title: Paper Review. Fully Convolutional Networks for Semantic Segmentation@CVPR' 2015
author: JooChan Park
date: 2019-07-25 18:00:00 +0800
categories: [Paper Reviews, Segmentation]
tags: [Segmentation, Semantic Segmenation, CV]
math: true
pin: False
---

- [Paper link](https://ieeexplore.ieee.org/abstract/document/8323240?casa_token=nbnxyMRMpUgAAAAA:zvlxwwUb0TsqpOtKJb5Fw4p-Synz9pT3foz9RiWCFkKTtt6GMoZplHw_Vvwqwdawvih9boY5984)


## **Abstract**
- 딥러닝을 이용한 Segmentation의 시초라고 할 수 있는 논문

- 이 논문은 fully convolution을 이용하여 어떻게 semantic segmentation을 deep learning으로 풀었는지 보여줌


## **Introduction**

### Semantic Segmentation이란?
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\1.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\2.PNG' width='800'>


## **Proposed Methods**

### Fully Convolutional Networks
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\3.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\4.PNG' width='800'>

### Deconvolution
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\5.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\6.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\7.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\8.PNG' width='800'>

### Skip layer
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\9.PNG' width='800'>

### Evaluation
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\10.PNG' width='800'>


## **Experiments**
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\11.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\12.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\13.PNG' width='800'>
<img src='\assets\papers\Fully_Convolutional_Networks_for_Semantic_Segmentation\14.PNG' width='800'>


## **Conclusions & Reviews**
- Fully connected layer를 Fully convolutional layer로 바꾸고 이전 layer의 정보를 이용해 upsampling하는 방법이 인상깊었음.

- Activation map의 크기를 낮췄다가 높이는 방식이므로 중간에 정보 손실이 발생해 윤곽선이 뚜렷하게 나오지 않음 -> Dilated Convolution : 필터 내부에 zero padding을 추가해 강제로 receptive field를 늘리는 방법


## **Reference**
