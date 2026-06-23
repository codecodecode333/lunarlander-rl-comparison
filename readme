# LunarLander RL Comparison

DQN 계열 강화학습 알고리즘의 성능을 비교하고 분석한 프로젝트입니다.

Gymnasium의 LunarLander-v2 환경에서 DQN, Double DQN(DDQN), Dueling DQN, D3QN(Double + Dueling)을 직접 구현하고 학습 성능을 비교했습니다.

---

## Project Overview

LunarLander는 강화학습에서 널리 사용되는 제어(Control) 문제입니다.

착륙선의 위치, 속도, 각도 등을 제어하여 중앙 착륙 지점에 안전하게 착륙시키는 것을 목표로 합니다.

본 프로젝트에서는 DQN 계열 알고리즘의 성능 차이를 분석하고, 과대평가 문제(Overestimation) 및 학습 안정성 개선 효과를 확인하는 것을 목표로 하였습니다.

---

## Environment

* LunarLander-v2
* Gymnasium
* Box2D

### State Space

총 8개 상태

* X Position
* Y Position
* X Velocity
* Y Velocity
* Angle
* Angular Velocity
* Left Leg Contact
* Right Leg Contact

### Action Space

| Action | Description       |
| ------ | ----------------- |
| 0      | Do Nothing        |
| 1      | Fire Left Engine  |
| 2      | Fire Main Engine  |
| 3      | Fire Right Engine |

---

## Implemented Algorithms

### DQN

기본 Deep Q-Network

* Experience Replay
* Target Network
* ε-Greedy Exploration

---

### Double DQN (DDQN)

Q-value 과대평가 문제를 해결하기 위해

* Action Selection
* Action Evaluation

을 분리하여 학습

---

### Dueling DQN

Q(s,a)를

* Value Stream V(s)
* Advantage Stream A(s,a)

으로 분해하여 학습

---

### D3QN

Double DQN + Dueling DQN

* 과대평가 감소
* 학습 안정성 향상
* 정책 품질 개선

---

## Network Structure

### DQN

Input(8)

→ Linear(128)

→ ReLU

→ Linear(128)

→ ReLU

→ Output(4)

---

### Dueling DQN

Input(8)

→ Shared Layers

→ Value Stream

→ Advantage Stream

→ Q(s,a)

---

## Hyperparameters

| Parameter     | Value       |
| ------------- | ----------- |
| Episodes      | 500         |
| Batch Size    | 64          |
| Replay Buffer | 50,000      |
| Gamma         | 0.99        |
| Learning Rate | 1e-3        |
| Target Update | 10 Episodes |

---

## Results

### Last 100 Episodes Average Reward

| Algorithm   | Average Reward |
| ----------- | -------------- |
| DQN         | -34            |
| DDQN        | 122            |
| Dueling DQN | 7              |
| D3QN        | 170            |

### Analysis

* DQN은 과대평가 문제로 인해 안정적으로 수렴하지 못함
* DDQN은 Q-value 안정성이 향상되어 높은 평균 보상을 기록
* Dueling DQN은 현재 학습량에서 충분히 수렴하지 못함
* D3QN은 가장 높은 평균 보상과 안정적인 정책을 보여줌

---

## Challenges & Solutions

### Problem 1

DQN의 Q-value Overestimation

### Solution

Double DQN 적용

* Action Selection
* Action Evaluation 분리

---

### Problem 2

학습 안정성 부족

### Solution

Dueling Network 적용

* State Value
* Advantage

분리 학습

---

## Future Work

* Moving Average 기반 Best Model 저장
* Rainbow DQN 적용
* Prioritized Experience Replay
* Noisy Network Exploration
* Distributional RL

---

## Tech Stack

* Python
* PyTorch
* Gymnasium
* Box2D
* NumPy
* Google Colab

---

## Author

Kim Minjae
