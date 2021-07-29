---
title: Paper Review. Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network@CVPR' 2017
author: JooChan Park
date: 2019-10-22 18:00:00 +0800
categories: [Paper Reviews, Super Resolution]
tags: [Super Resolution, GAN, CV]
math: true
pin: False
---

- [Paper link](https://openaccess.thecvf.com/content_cvpr_2017/html/Ledig_Photo-Realistic_Single_Image_CVPR_2017_paper.html)


## **Super Resolution이란?**
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\1.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\2.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\3.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\4.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\5.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\6.PNG' width='800'>


## **딥러닝 SR의 시작 – SRCNN**
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\7.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\8.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\9.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\10.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\11.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\12.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\13.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\14.PNG' width='800'>


## **딥러닝 SR의 발전 – VDSR**
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\15.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\16.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\17.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\18.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\19.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\20.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\21.PNG' width='800'>


## **딥러닝 SR의 발전 – SRGAN**
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\23.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\24.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\25.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\26.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\27.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\28.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\29.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\30.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\31.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\32.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\33.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\34.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\35.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\36.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\37.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\38.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\39.PNG' width='800'>
<img src='\assets\papers\Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network\40.PNG' width='800'>

## **Conclusions & Reviews**
- Object detection같은 경우 input image data를 Super resolution으로 화질 개선하여 사용하면 성능이 올라갈 것이다. 하지만 image의 크기가 2배or 4배 가량 커지기 때문에 memory문제가 발생할 수 있음.

- 명확하고 신뢰할 수 있는 하나의 평가 지표가 없어 PSNR, SSIM, MOS와 같이 여러 지표를 비교해가며 성능을 확인해야 함

- Method를 선택할 때, PSNR, SSIM, MOS 중에서 어떤 것을 중점으로 보고 선택하고 사용해야 할지 고르기가 힘들 것 같음


## **Reference**
1.  https://hoya012.github.io/
2.  https://www.slideshare.net/NaverEngineering/deep-learning-super-resolution
3.  https://leedakyeong.tistory.com/
4.  Image Super-Resolution Using Deep Convolutional Networks, 2014 ECCV
5.  Accurate Image Super-Resolution Using Very Deep Convolutional Networks, 2016 CVPR
6.  Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network, 2016 arXiv
7.  Deep Learning for Single Image Super-Resolution: A Brief Review, 2018 arXiv
8.  A Deep Journey into Super-resolution: A Survey, 2019 arXiv
