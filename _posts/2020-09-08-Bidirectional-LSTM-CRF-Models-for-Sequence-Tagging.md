---
title: Paper Review. Bidirectional LSTM-CRF Models for Sequence Tagging@arXiv' 2015
author: JooChan Park
date: 2020-09-08 13:00:00 +0800
categories: [Paper Reviews, Tagging]
tags: [LSTM, Tagging, NLP]
math: true
pin: false
---

- [Paper link](https://arxiv.org/abs/1508.01991)

## **Abstract**
- LSTM 레이어와 CRF 레이어를 이용하여 LSTM-CRF 모델을 만듦

- BI-LSTM 레이어와 CRF 레이어를 이용하여 BI-LSTM-CRF 모델을 만듦

- BI-LSTM-CRF 모델을 이용하면 POS tagging태스크에서 높은 성능을 도달할 수 있음


## **Introduction**

### CRF란
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\1.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\2.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\3.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\4.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\5.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\6.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\7.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\8.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\9.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\10.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\11.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\12.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\13.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\14.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\15.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\16.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\17.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\18.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\19.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\20.PNG' width='800'>

### Feature Function
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\21.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\22.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\23.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\24.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\25.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\26.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\27.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\28.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\29.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\30.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\31.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\32.PNG' width='800'>

## **Proposed Method**

### Models
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\33.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\34.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\35.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\36.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\37.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\38.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\39.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\40.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\41.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\42.PNG' width='800'>

### LSTM-CRF Model
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\43.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\44.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\45.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\46.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\47.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\48.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\49.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\50.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\51.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\52.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\53.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\54.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\55.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\56.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\57.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\58.PNG' width='800'>

### BI-LSTM-CRF Model
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\59.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\60.PNG' width='800'>

## **Experiments**
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\61.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\62.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\63.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\64.PNG' width='800'>
<img src='\assets\papers\Bidirectional LSTM-CRF Models for Sequence Tagging\65.PNG' width='800'>


## **Conclusions & Reviews**
- POS tagging과 같이 규칙이 있는 알고리즘일 경우 CRF를 사용하는 것이 의미가 있음 (예. 부사 뒤에 부사가 올 수 없음)

- CRF의 feature function을 정의하기 위해서는 모든 경우의 수를 고려해야함

- Feature function이 많아질수록 연산량이 많아 속도가 느려질 텐데 보통 몇 개인지 궁금함

- CRF를 사용하면 속도가 많이 느려질 텐데 속도에 대한 실험 결과가 없어 아쉬움


## **Reference**
