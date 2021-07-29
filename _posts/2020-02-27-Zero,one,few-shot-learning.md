---
title: Zero One Few Shot Learning
author: JooChan Park
date: 2020-02-27 19:00:00 +0800
categories: [Documentations, Probability]
tags: [Probability]
math: true
pin: False
---

## **Introduction**
[CS109](https://web.stanford.edu/class/archive/cs/cs109/cs109.1196/schedule.html), Lecture 21 MLE부분을 공부하면서 zero, one shot learning에 대한 예시가 나왔는데 이해가 부족하여 정리해보려 한다. 먼저 zero-shot leaning이 무엇인지부터 시작해 one-shot leaning, few-shot learning이 무엇인지 살펴보도록 하겠다.

## **Contents**
### Zero Shot Learning
Zero-shot learning이란 학습에 한번도 보지 못했던 데이터를 분류하기 원하는 학습 방법이다. 예를 들어 자전거라는 데이터가 많아 자전거 클래스에 대해서 성공적으로 학습을 했는데 테스트 이미지로 오토바이가 갑자기 나타났다고 하자. 우리가 원하는 것은 모델이 오토바이라는 자전거와 가까운 클래스를 만들어 주는 것이다. 하지만 기존 모델들은 한번도 못 본 이미지를 새로운 클래스로 분류할 수 없었다. 그래서 이러한 문제를 해결하기 위해 만든 방법이 zero-shot learning이다. 알아서 새로운 클래스를 만들어 분류해주는 방법이다. 많은 데이터가 필요한 딥러닝에서 레이블링이 된 수많은 카테고리에 대한 데이터를 수집하기 어렵기 때문에 zero-shot learning이 필요하다.

### One Shot Learning
One-shot leaning이란 새로운 클래스에 대해 데이터 샘플이 단 한 개만 주어지고 이를 구별하는 것이다. 예를 들어 여러 개의 자전거가 있다고 하자. 사람이라면 자전거에 대해 아무런 지식이 없더라도 자전거 이미지 한 장만 보면 자전거라는 개념을 바로 학습할 수 있다. 그 이후로는 단 한번도 본적 없는 특이한 모양의 자전거를 본다면 “자전거”라는 사실을 바로 알아낼 수 있다. 하지만 일반적인 딥러닝 네트워크들은 한 클래스를 학습하기 위해 수백 또는 수천장이 넘는 이미지가 필요하다. 한 클래스에 대한 이미지가 수백 또는 수천장을 갖고 레이블링이 된 상태가 아니라면 딥러닝에 사용하기 어렵다. 그렇게 때문에 적은 이미지로도 학습하는 방법이 매우 중요하며 이를 해결하는 방법 중 하나는 one-shot learning이다. 

### Few Shot Learning
Few-shot learning이란 아주 적은 몇 장의 이미지로 데이터의 특징을 뽑아 식별할 수 있도록 하는 것이다. One-shot leaning에서는 한 장의 이미지만 보았다면 few-shot learning은 많지는 않지만 적은 양의 이미지만 가지고 이미지 분류를 하는 것이다. 

## **Conclusion**
Zero, one, few shot learning모두 데이터의 수가 제한적이기 때문에 등장한 방법론이다. 많은 데이터를 이용해 복잡한 모델을 사용하여 이미지 분류를 잘 이끌어내는 연구 방법과는 반대로 적은 데이터로 이미지를 잘 분류하고자 방법론들이다.

## **Reference**
1.	https://towardsdatascience.com/applications-of-zero-shot-learning-f65bb232963f 
2.	https://jayhey.github.io/
3.	https://www.kakaobrain.com/blog
