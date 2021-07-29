---
title: GRU Backpropagation
author: JooChan Park
date: 2019-10-01 19:00:00 +0800
categories: [Documentations, Deep Learning]
tags: [Deep Learning]
math: true
pin: False
---

## **Introduction**
LSTM에서는 출력, 입력, 삭제 게이트라는 3개의 게이트가 존재했었다. 반면, GRU에서는 업데이트 게이트와 리셋 게이트 두 가지 게이트만이 존재한다. GRU는 LSTM보다 게이트 수가 하나 적어 학습 속도면에서는 빠르지만 성능면에서는 LSTM이 GRU보다 성능이 뛰어나다는 것으로 알려져 있다. 이 문서에서는 GRU의 게이트를 살펴보고 GRU의 weigth들이 어떻게 Update되는지 Backpropagation을 통해 살펴보도록 하겠다.

## **Contents**
<img src='\assets\doc\GRU Backpropagation\GRU Backpropagation-1.png' width='900'>
<img src='\assets\doc\GRU Backpropagation\GRU Backpropagation-2.png' width='900'>
<img src='\assets\doc\GRU Backpropagation\GRU Backpropagation-3.png' width='900'>

## **Conclousion**
GRU에서 각 게이트의 파라미터 들이 어떻게 update되는지 살펴보았다. LSTM에 비해 게이트 수가 하나 적은 만큼 성능이 비교적 떨어지는 것 같고, 일반적인 경우에는 LSTM을 사용한다.

## **Reference**
1.	https://medium.com/ 
