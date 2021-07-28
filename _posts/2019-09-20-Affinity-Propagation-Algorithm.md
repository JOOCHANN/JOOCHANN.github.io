---
title: Affinity Propagation Algorithm
author: JooChan Park
date: 2019-09-20 19:00:00 +0800
categories: [Documentations, Deep Learning]
tags: [Deep Learning]
math: true
pin: true
---

## **Introduction**
비지도 학습의 과업에는 군집화, 밀도 추정, 공간변환 이렇게 크게 세가지로 나눌 수 있다. 이중 군집화의 한 종류인, Affinity Propagation Algorithm에 대해서 알아보려고 한다. Affinity Propagation Algorithm는 모든 데이터가 특정한 기준에 따라 자신을 대표할 대표 데이터를 선택한다. 만약 스스로가 자기 자신을 대표하게 되면 클러스터의 중심이 된다. 군집의 개수를 k라고 했을 때, K-means 알고리즘과는 다르게 이것을 hyperparameter로써 선택해 주는 것이 아니라 자동으로 알아낸다. Responsibility, Availability라는 두 종류의 친밀도 행렬을 이용하여 군집화 한다. Responsibility, Availability행렬이 무엇인지 자세히 알아보고 알고리즘이 어떻게 동작하는지 살펴보려고 한다.

## **Contents**
<img src='\assets\doc\Affinity Propagation Algorithm\Affinity Propagation Algorithm-1.png' width='900'>
<img src='\assets\doc\Affinity Propagation Algorithm\Affinity Propagation Algorithm-2.png' width='900'>
<img src='\assets\doc\Affinity Propagation Algorithm\Affinity Propagation Algorithm-3.png' width='900'>
<img src='\assets\doc\Affinity Propagation Algorithm\Affinity Propagation Algorithm-4.png' width='900'>

## **Conclousion**
K-means의 알고리즘은 군집의 개수와, 초기 군집대표의 값을 정해주어야 하며 초기 군집의 값을 어떻게 설정해주는지에 대해 결과가 달라진다. 하지만 Affinity Propagation Algorithm은 군집의 개수와, 초기 군집대표의 값을 정해주지 않아도 되며, 자가 유사도 $$ s(k, k) $$의 값을 어떻게 설정해주는지에 따라 군집의 개수가 달라진다는 차이점이 있다. 비지도 학습은 크게 군집화, 밀도 추정, 공간 변환으로 나눌 수 있는데 이 중 군집화에 한 종류인 Affinity Propagation Algorithm에 대해 살펴 보았다.

## **Reference**
1.	https://www.geeksforgeeks.org/
2.	오일석, 기계학습, 한빛아카데미, p323~325
