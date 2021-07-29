---
title: Paper Review. Attention is all you need@NIPS' 2017
author: JooChan Park
date: 2020-09-29 13:00:00 +0800
categories: [Paper Reviews, Machine Translation]
tags: [Attention, Machine Translation, NLP]
math: true
pin: true
---

- [Paper link](https://proceedings.neurips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf)

## **Abstract**
- 당시 가장 좋은 모델은 Attention 메커니즘을 통해 encoder와 decoder를 연결한 모델이 성능이 가장 좋음

- 기존 모델들처럼 RNN또는 CNN을 사용하지 않고 attention 메커니즘만을 기반으로 하는 Transformer 모델을 제안함

- 기계 번역 태스크 실험을 통해 모델이 병렬화 가능하며, 학습 시간이 단축되는 것을 보임

## **Introduction**
<img src='\assets\papers\Attention is all you need\1.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\2.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\3.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\4.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\5.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\6.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\7.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\8.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\9.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\11.PNG' width='800'>


## **Proposed Method**

### Model Architecture
<img src='\assets\papers\Attention is all you need\12.PNG' width='800'>

### Positional Encoding
<img src='\assets\papers\Attention is all you need\13.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\14.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\15.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\16.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\17.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\18.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\19.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\20.PNG' width='800'>

### Encoder
<img src='\assets\papers\Attention is all you need\21.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\22.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\23.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\24.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\25.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\26.PNG' width='800'>

### Multi-Head Attention
<img src='\assets\papers\Attention is all you need\27.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\28.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\29.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\30.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\31.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\32.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\33.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\34.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\35.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\36.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\37.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\38.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\39.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\40.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\41.PNG' width='800'>

### Position-Wise FC Layer
<img src='\assets\papers\Attention is all you need\42.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\43.PNG' width='800'>

### Decoder
<img src='\assets\papers\Attention is all you need\44.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\45.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\46.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\47.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\48.PNG' width='800'>

### Why Self-Attention
<img src='\assets\papers\Attention is all you need\49.PNG' width='800'>


## **Training**
<img src='\assets\papers\Attention is all you need\50.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\51.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\52.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\53.PNG' width='800'>


## **Experiments**
<img src='\assets\papers\Attention is all you need\54.PNG' width='800'>
<img src='\assets\papers\Attention is all you need\55.PNG' width='800'>


## **Conclusions & Reviews**
- Machine Translation 태스크에서 Transformer 모델은 빠르게 학습하며, 성능도 우수하다는 것을 보여줌

- Recurrent 모델을 사용하지 않고도 sequential 데이터를 처리할 수 있는 모델

- Encoder와 decoder에서 attention을 통해 query와 가장 밀접한 연관성을 가지는 value를 강조 할 수 있음

- 모델 병렬화가 가능해짐

- Attention을 다시 정리하면서 공부할 수 있었음


## **Reference**
