---
title: Softmax & Cross Entropy
author: JooChan Park
date: 2019-08-29 19:00:00 +0800
categories: [Documentation, Deep Learning]
tags: [Documentation]
math: true
pin: true
---

## **Introduction**
Softmax 함수가 무엇인지 알기 위해 먼저 순차적으로 정보이론, Shannon entropy, Kullback-Leibler divergence, 그리고 Cross entropy에 대해서 살펴본다. 
마지막으로 Softmax 함수가 어떻게 Backpropagation되어 weigth이 update 되는지 살펴 보도록 한다.

## **Contents**
<img src='\assets\doc\Softmax, Cross entropy\Softmax, Cross entropy-1.png' width='900'>
<img src='\assets\doc\Softmax, Cross entropy\Softmax, Cross entropy-2.png' width='900'>
<img src='\assets\doc\Softmax, Cross entropy\Softmax, Cross entropy-3.png' width='900'>
<img src='\assets\doc\Softmax, Cross entropy\Softmax, Cross entropy-4.png' width='900'>
<img src='\assets\doc\Softmax, Cross entropy\Softmax, Cross entropy-5.png' width='900'>
<img src='\assets\doc\Softmax, Cross entropy\Softmax, Cross entropy-6.png' width='900'>

## **Conclusion**
Softmax 함수가 무엇인지 구체적으로 알게 되었으며, 실제 Score와 Softmax를 통해 나온 확률 값을 어떻게 비교해야 하는지도 알게 되었다. Loss를 softmax 함수 x에 대해 backpropagation을 해봄으로써 x가 변화할 때의 Loss의 변화량을 알게 되었다.

## Reference
1.	https://ratsgo.github.io/
2.	https://brunch.co.kr/
3.	https://selfish-developer.com/
