---
title: Negative Sampling
author: JooChan Park
date: 2019-10-10 19:00:00 +0800
categories: [Documentations, Deep Learning]
tags: [Deep Learning]
math: true
pin: False
---

## **Introduction**
Negative sampling은 Word2vec의 training방법중 하나이다. Negative sampling이 무엇인지 살펴보기 전에 먼저 Word2vec란 무엇인지 간단하게 알아보고, Word2vec의 두가지 방식인 CBOW, skip-gram에 대해서 간단히 알아보고, 마지막으로 단어가 벡터로 잘 바뀔 수 있도록 training시키는 방법중 하나인 Negative sampling에 대해서 자세히 다루겠다.

## **Contents**
<img src='\assets\doc\negative sampling\negative sampling-1.png' width='900'>
<img src='\assets\doc\negative sampling\negative sampling-2.png' width='900'>
<img src='\assets\doc\negative sampling\negative sampling-3.png' width='900'>

## **Conclousion**
Word2vec를 training 할 때, negative sampling을 한다면 성능이 향상되고 계산량이 낮아지므로 좋은 training 기법이라고 할 수 있다.

## **Reference**
1.	Y. Goldberg, et al., word2vec Explained: Deriving Mikolov et al.’s Negative-Sampling Word-Embedding Method. https://brunch.co.kr/
2.	https://ratsgo.github.io/ 
3.	http://solarisailab.com/ 

