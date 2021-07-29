---
title: Paper Review. Scale-aware Automatic Augmentation for Object Detection@CVPR' 2021
author: JooChan Park
date: 2021-07-14 13:00:00 +0800
categories: [Paper Reviews, Augmentation]
tags: [Augmentation, Object Detection]
math: true
pin: true
---

- [Paper link](https://openaccess.thecvf.com/content/CVPR2021/html/Chen_Scale-Aware_Automatic_Augmentation_for_Object_Detection_CVPR_2021_paper.html)

## **Abstract**
- Object detection task에서 최적의 augmentation policy를 찾는 **scale-aware AutoAug**방법을 제안함
- Scale 불변성을 유지하기 위해 image-level과 box-level에서 augmentation을 진행한 **scale-aware search space**를 정의함
- Object detection task에서 주로 사용하는 AutoAugment-det, RandAugment 보다 우수함

## **Introduction**
- Data Augmentation
    - Color operations : Brightness, contrast, and whitening …
    - Geometric operations : Re-scaling, and flip …

### AutoAug-det[1]
- Object detection의 data augmentation policy
- Main idea : Classification에 사용되는 데이터셋보다 detection을 위한 데이터셋의 수가 더 적기 때문에, **bounding box** 값 변화를 함께 주어야함

<img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img1.png' width='300'>

- 박스의 context를 보고 color or geometric augmentation을 수행하는 방법으로 총 세가지 operation이 있다고 보면 됨
    1. Color operations : 이미지의 color 값을 변환하되, bounding box의 위치 좌표 값에는 변화를 주지 않음 
    ex) Equalize, contrast, brightness …

    2. Geometric operations : 이미지의 위치정보를 바꾸며, bounding box의 위치나 사이즈를 같이 변화함 
    ex) Rotate, shearX, tanslationY …

    3. Bounding box operations : 이미지 내에서 bounding box가 있는 부분의 픽셀만 변화시킴 
    ex) Bbox_Only_Equalize, Bbox_Only_Rotate …
- Training 과정에서만 data augmentation을 수행하며, 하나의 이미지에 대해 순차적으로 여러 개의 augmentation이 적용되는데 어떤 순서로 사용할지 search method를 통해 최적화 시킴

- Search space의 계산

    $$ (22𝐿𝑀)^{𝑁𝐾}=(22×6×6)^{2×5}≈9.6×{10}^{28} $$

- 각각 N개의 순차적인 transformation operands를 갖는 K개의 sub-policy를 학습하고, training 과정에서 각 이미지에 적용될 policy가 랜덤으로 선택됨
- M은 transformation이 적용될 확률, L은 transformation이 적용될 크기(magnitude)
- 문제점1 : object detection의 필수적인 image와 box level의 크기 문제를 고려하지 않았음
- 문제점2 : 연산량이 매우 큼 (400 TPU for 2days)

-본 논문에서는 객체 탐지를 위한 자동적으로 학습하는 scale-aware data augmentation 전략을 제안함-

### Review of AutoAug
- Auto augmentation
    - 세가지의 메인 구성 요소로 이루어짐
        1. Search space : 얼마만큼의 augmentation 종류가 존재하는지
        2. Search algorithm : 어떻게 좋은 augmentation을 선택할 것인지
        3. Estimation metric : 어떻게 좋은 augmentation을 평가할 것인지

### Scale-Aware Search Space
- Motivation
    - 저자들은 오브젝트 박스 이외의 pixel을 지우고 학습하여 성능 차이를 비교해 봄
    - 그 결과 small object의 경우 주변 pixel이 중요함을 알 수 있으며, 이는 학습 모델이 모든 크기의 객체를 적절히 처리하지 못할 수 있음
    - Bounding box의 scale에 따라 augmentation을 다르게 해주는 area ratio를 제안함

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img2.png' width='800'>
    _Fig2. Motivation_

- Image-level augmentations
    - Probabilities 𝑃
        - $$𝑃_{𝑜𝑢𝑡}$$이 선택될 확률 : $$×0 ~ ×0.5$$
        - $$𝑃_{𝑖𝑛}$$이 선택될 확률 : $$×0 ~ ×0.5$$
        - $$𝑃_{𝑜𝑟𝑖}$$이 선택될 확률 : $$1−𝑃_{𝑖𝑛}−𝑃_{𝑜𝑢𝑡}$$
    - Magnitudes 𝑀.
        - $$𝑃_{𝑜𝑢𝑡}$$의 크기 : $$×1.0 ~ ×1.5$$
        - $$𝑃_{𝑖𝑛}$$의 크기 : $$×0.5 ~ ×1.0$$
        - $$𝑃_{𝑜𝑟𝑖}$$의 크기 : $$×1.0$$
    - Zoom-in operation
        - probability range : 6 discrete values $$[0, 0.1, 0.2, 0.3, 0.4, 0.5]$$
        - magnitude range : 6 discrete values $$[0.5, 0.6, 0.7, 0.8, 0.9, 1.0]$$
    - Zoom-out operation
        - probability range : 6 discrete values $$[0, 0.1, 0.2, 0.3, 0.4, 0.5]$$
        - magnitude range : 6 discrete values $$[1.0, 1.1, 1.2, 1.3, 1.4, 1.5]$$

- Box-level augmentations 
    - 8 color operations와 6 geometric operations 존재
        - probability range : 6 discrete values $$[0, 0.2, 0.4, 0.6, 0.8, 1.0]$$
        - magnitude range : 6 discrete values $$[0, 2, 4, 6, 8, 10]$$

    - Area ratio (scale ratio)
        - area ratio type : small, middle, large
        - area ratio range : 10 discrete values $$[0.2, 0.4, 0.6, 0.8, 1.0, 2, 4, 6, 8, 10]$$

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img3.png' width='800'>
    _Fig3. Image-level, and box-level augmentations_   

- Box-level augmentations의 효과
    1. Gaussian을 통한 부드러운 augmentation

    $$ 𝐴=𝛼(𝑥,𝑦)∙𝐼+(1−𝛼(𝑥,𝑦))∙𝑇 $$

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img4.png' width='800'>
    _Fig4. An example of Gaussian-based box-level augmentation_

    2. Area ratio라는 학습 가능한 파라미터
    - Area ratio $$r$$에 따라 표준편차를 다르게 적용하여 $$r$$이 크면 $$𝑟(𝑠_{𝑏𝑜𝑥})$$가 더 넓은 범위로 augmentation이 자연스럽게 적용됨
    - 반대로 $$r$$이 작으면 $$𝑟(𝑠_{𝑏𝑜𝑥})$$가 더 작아져 부분적으로 augmentation이 적용됨

    $$ 𝛼(𝑥,𝑦)=exp⁡(−((𝑥−𝑥_𝑐)^2/(2𝜎_𝑥^2))+((𝑦−𝑦_𝑐)^2/(2𝜎_𝑦^2))) $$

    $$ 𝑉=∫_0^𝐻∫_0^𝑊𝛼(𝑥,𝑦)d𝑥d𝑦 $$

    $$ 𝜎_𝑥=ℎ\sqrt{(𝑊/𝐻)/2𝜋}∙𝑟,  𝜎_𝑦=𝑤\sqrt{(𝐻/𝑊)/2𝜋}∙𝑟 $$

    $$ 𝑟(𝑠_{𝑏𝑜𝑥})=𝑉/𝑠_{𝑏𝑜𝑥} $$

- Search space summary
    - Image-level augmentation : $$(6^2)^2$$
        - Zoom-in : $$6×6$$
        - Zoom-out : $$6×6$$

    - Box-level augmentation : $$({10}^3)×((8×6×6)×(6^3))^5$$
        - Area ratio : $$10×10×10$$
        - Color operation : $$8×6×6$$
        - Geometric operation : $$6×6×6$$
        - Box-level operation은 총 5개의 sub-policy로 구성, 1개의 sub-policy는 2개의 augmentation으로 구성 (color, geometric operation)

    - Total search space : $$({(6^2)}^2×{10}^3)×{((8×6×6)×(6^3))}^5=(1.2)^{30}$$

### Scale-Aware Estimation Metric
- “Balanced optimization over different scales”이 중요하다고 생각하여 search 과정 중에 different scale별로 accumulated loss와 accuracy를 이용함

    $$ min_𝑝⁡𝑓(\{𝐿_{(𝑖∈𝑆)}^𝑝\}, \{(AP)_{(𝑖∈𝑆)}^𝑝\}) $$

    - $$ \{(AP)_{(𝑖∈𝑆)}^𝑝\} $$ : Data augmentation policy $$𝑝$$로 학습한 plain model의 각 scale $$𝑖$$별로 validation accuracy $$(𝐴𝑃)_𝑖$$
    - $$ \{𝐿_{(𝑖∈𝑆)}^𝑝\} $$ : Data augmentation policy $$𝑝$$로 학습한 plain model의 각 scale $$𝑖$$별로 Accumulated loss $$𝐿_𝑖$$
    - 다른 scale별로 balanced optimization은 필수적이며, 간단하게 다양한 scale별로 loss의 standard deviation을 측정하면 되지만, 이는 sub-optimal에 빠지게 됨
    - 그래서 Pareto Optimality[2]를 수행함
    - Pareto Optimality[2]이란[3]
        - 자원 배분이 가장 효율적으로 이루어진 상태를 pareto optimal이라고 함
        Pareto는 손해를 보는 사람은 하나도 없고 이익을 보는 사람만 있는 경우를 pareto 개선이라고 함
        - Pareto 개선이 불가능할 정도로 개선된 상태를 pareto optimal이라고 함
        즉, 모든 사람이 타인의 불만을 사는 일 없이는 자기 만족을 더 이상 증가시킬 수 없는 상태가 '파레토 최적’ 임

- Objective function
    - Pareto optimality에 의해 “The optimization over scales can not be better without hurting the accuracy of any other scale” 라는 개념을 가져옴

    $$ min_𝑝⁡𝑓(\{𝐿_{(𝑖∈𝑆)}^𝑝\}, \{(AP)_{(𝑖∈𝑆)}^𝑝\}) = 𝜎(\{𝐿_{(𝑖∈𝑆)}^𝑝\})∙Φ(\{(AP)_{(𝑖∈\hat 𝑆)}^𝑝\})$$

    $$ Φ(\{(AP)_{(𝑖∈\hat 𝑆)}^𝑝\})=∏_{(𝑖∈\hat 𝑆)}{({𝐴𝑃}_𝑖)}/{({𝐴𝑃}_𝑖^𝑝)}$$

    - Policy $$𝑝$$을 통하여 fine-tuning 했을 때, 성능 저하가 발생하는 scale $$𝑆$$ ̂에 처벌을 주는 penalization factor $$Φ$$를 제안함
    - $${({𝐴𝑃}_𝑖)}/{({𝐴𝑃}_𝑖^𝑝)}$$ : scale-wise ratio of original and the fine-tuned accuracy

- Autoaugment 방법은 일반적으로 proxy task(훈련 이미지가 있는 작은 하위 집합)에 대한 validation accuracy를 search metric으로 사용함. 실험 결과, proxy task에서 accuracy로 구한 policy와 scale-aware metric을 이용하여 구한 policy를 실제 dataset에서 성능을 측정하였을 때, coefficent가 더 높음

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img5.png' width='400'>
    _Fig5. Coefficients between actual accuracy and metrics_

### Search algorithm
- Sample dataset에서 scale-aware estimation metric이 제일 최소가 되도록 fine-tuning하여 최적의 augmentation policy를 찾음
- Scratch부터 학습하면 시간이 오래 걸리기에, data augmentation없이 학습한 plain model을 augmentation policy로 fine-tuning하여 시간을 줄임

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img6.png' width='400'>
    _Fig6. Search algorithm_


## **Experiments**
- Detector별 성능 지표

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img7.png' width='400'>
    _Fig7. Comparison with object detection augmentation strategies on MS COCO dataset_

- Improvement details on RetinaNet ResNet-50

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img8.png' width='400'>
    _Fig8. Improvement details_

- Comparison with AutoAug-det on RetinaNet ResNet-50

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img9.png' width='400'>
    _Fig9. Comparison with AutoAug-det_

- Search on RetinaNet ResNet-50 with different metrics

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img10.png' width='400'>
    _Fig10. Different scale-aware estimation metrics_

- Improvements across detection and segmentation frameworks

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img11.png' width='800'>
    _Fig11. Different frameworks_

- Comparison with SOTA data augmentation methods for object detection

    <img src='\assets\papers\Scale aware Automatic Augmentation for Object Detection\img12.png' width='800'>
    _Fig12. Comparison with SOTA data augmentation methods_

## **Conclusions & Reviews**
- Augmentation policy를 찾는데 20 GPU-days가 걸리며, 다른 RL을 사용한 auto augmentation방법보다 빠르지만, 여전히 시간이 오래 걸림
- 데이터가 적은 object detection task에 좋음
- Box level에서 데이터 augmentation하는 것과 가우시안 분포를 활용하여 이미지를 자연스럽게 변환하는 기법이 효과적인 것 같음

## **Reference**
1.  Zoph, Barret, et al. "Learning data augmentation strategies for object detection." European Conference on Computer Vision. Springer, Cham, 2020.
2.  John Black, Nigar Hashimzade, and Gareth Myles. A dictionary of economics. Oxford university press, 2012
3. http://www.aistudy.co.kr/economics/pareto_optimal.htm

