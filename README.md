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

      

