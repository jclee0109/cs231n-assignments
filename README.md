# cs231n-assignments

# assignments2
## 3. Drop-out
# 0. Background Knowledge
1. Optimization
    1. What?
        - Neural Network를 빠르게 훈련시키는 최적화 알고리즘
    2. Why?
        - 데이터가 많아지면 학습속도가 느려지는데, 이것을 빠르고 효율적으로 최적 값을 찾게 도와주기 위함
    3. How?
        1. Gradient Descent (참고 https://velog.io/@minjung-s/Optimization-Algorithm)
        - 가장 기본적인 방법
        - ![image](https://user-images.githubusercontent.com/65020700/188276191-fe279c4a-64eb-4f6a-a9af-eecf43fdf855.png)
        - Batch(전체 데이터 사용), Mini-Batch(일부 데이터 사용, 기울기는 각 데이터 평균), Stochastic(하나의 데이터 사용)으로 나뉨
        - ![image](https://user-images.githubusercontent.com/65020700/188276750-592f31c2-165a-4f05-9513-1aa3a10dbd73.png)
        2. Momentum Algorithm (기울기 속도 강화)
        - 지수가중평균!! (오래된 데이터가 미치는 영향을 지수적으로 감쇠하도록 만들어주는 방법
        - 최근의 데이터들로만 Gradient Descent를 하고 싶을 수 있다! 이럴 때 사용
        - ![image](https://user-images.githubusercontent.com/65020700/188282219-8a7b0c96-705e-485b-a56b-e06085174bfb.png)
        - 예전 데이터는 β^n으로 지수적으로 빠르게 감소하게 되기 때문에, 지수적(Exponetially) 감쇠라고 부른다.
        - ![image](https://user-images.githubusercontent.com/65020700/188282321-77ffe039-5771-4dbb-af24-85430e8d64a3.png)
        - 주로 β=0.9를 사용! -> Learning rate는 자연스럽게 0.1로
        3. RMS Prop Algorithm
        - ![image](https://user-images.githubusercontent.com/65020700/188282426-c05df948-2d2a-4980-8dcd-6e7e70e93833.png)
        4. Adam Optimization Algorithm (Momentum + RMS Prop)
        - ![image](https://user-images.githubusercontent.com/65020700/188282486-ba839d0a-84c3-4fa6-8a99-0d8b870ce5c3.png)
2. CNN
    1. what?
        - Convolutional Neural Networks
        - 주로 이미지나 영상 데이터를 처리할 때 사용
        - Convolution이 주요 아이디어인 모델 (Convolution : Kernel을 통해 연산, Convolution Operation)
        - 이미지 전체보다는 부분을 보는 것, 한 픽셀과 주변 픽셀들과의 연관성을 살리는 것
    2. why?
        - DNN을 개선하기 위해 도입
        - DNN은 보통 Flatten을 통해 계산
        - 이미지의 공간적/지역적 정보가 손실
        - 추상화 과정 없이 바로 연산과정 : 학습시간, 효율 저하
        - ![image](https://user-images.githubusercontent.com/65020700/188305375-d35a4c9d-ac25-4ef4-ac23-d7ed8b17c597.png)
        - 새의 부리모양, 날개모양 등을 통해 새라는 것을 인지 -> Flatten을 사용하면 이러한 부분이 왜곡될 우려가 있음
        - 전체보다는 부분을 보는 것이 이미지 인식에 더욱 효율적일수도 있음 (Kernel의 크기를 정하는 의미가 이렇게 부분을 보겠다는 의미가 될 수도 있을 것 같습니다.)
    3. how?
        - Convolution -> Relu -> Pool -> Conv -> Relu -> Pool -> ... -> Flatten -> Classification -> Activation Function
        - Zero Padding : Convolution을 하면 외각쪽의 값들은 비중이 줄어드는데 이것을 보완해주기 위해 외각에 0 element들을 덧붙여 주는 것
        - stride : 건너뛰기, 연산량 감소 효과? (#TODO : Stride 사용 이유 리서치) 
        - activation : "A neural network without an activation function is just a linear regression model." -> 레이어가 깊어저도 똑같이 그냥 선형 회귀에 불과하다.
        - Linear, Sigmoid, Hyperbolic, ReLU, LeakyReLU, Softmax

3. Dropout
    1. what?
        - Drop-out은 서로 연결된 연결망(layer)에서 0부터 1 사이의 확률로 뉴런을 제거(drop)하는 기법
    2. why?
        - 특정한 변수(feature)가 영향을 너무 많이 끼치는 것을 방지하기 위함 -> Overfitting 방지를 위함
        - Drop-out을 적용하지 않고 모델을 학습하면 해당 Feature에 가중치가 가장 크게 설정되어 나머지 Feature에 대해서는 제대로 학습되지 않을 것
    3. how?
        - ![image](https://user-images.githubusercontent.com/65020700/188355067-14667176-7dab-481b-bbe0-8115b279fd67.png)
        - https://kratzert.github.io/2016/02/12/understanding-the-gradient-flow-through-the-batch-normalization-layer.html

