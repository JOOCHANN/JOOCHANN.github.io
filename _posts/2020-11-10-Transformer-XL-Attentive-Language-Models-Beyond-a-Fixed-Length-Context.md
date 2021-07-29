---
title: Paper Review. Transformer-XL Attentive Language Models Beyond a Fixed-Length Context@ACL' 2019
author: JooChan Park
date: 2020-11-10 13:00:00 +0800
categories: [Paper Reviews, Machine Translation]
tags: [Attention, Machine Translation, NLP]
math: true
pin: false
---

- [Paper link](https://arxiv.org/abs/1901.02860)

## **Abstract**
- 기존의 transformer는 고정된 개수(512)의 token들을 갖는 한 개의 segment만을 input으로 사용하여, 연속된 segment들 간의 dependency를 반영하지 못함

- 현재 segment를 처리할 때, 이전 segment를 처리할 때 계산된 hidden state들을 사용하는 recurrence를 추가하여 위 문제를 해결함

- 모델에 적합한 positional encoding을 변형하였음

- Transformer-XL은 language modeling에서 SOTA의 성능을 기록함


## **Introduction**

### Transformer
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\1.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\2.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\3.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\4.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\5.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\6.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\7.PNG' width='800'>


## **Proposed Method**

### Vanilla Transformer Language Model
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\8.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\9.PNG' width='800'>

### Segment-Level Recurrence with State Reuse
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\10.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\11.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\12.PNG' width='800'>

### Relative Position Encoding
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\13.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\14.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\15.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\16.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\17.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\18.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\19.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\20.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\21.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\22.PNG' width='800'>

### Transformer XL
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\23.PNG' width='800'>

## **Experiments**
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\25.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\26.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\27.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\28.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\29.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\30.PNG' width='800'>
<img src='\assets\papers\Transformer-XL Attentive Language Models Beyond a Fixed-Length Context\31.PNG' width='800'>


## **Conclusions & Reviews**
- RNN 계열 모델과 vanilla Transformer model보다 long-term dependency를 더 잘 잡아냈음

- 이전 segment를 저장해두고 사용함으로써 prediction시 상당한 속도 향상을 달성함

- Recurrence 방법을 사용하기 위해 relative position encoding을 수식적으로 풀어서 의미부여를 하고, 적용한 것이 대단하다고 느낌


## **Reference**
