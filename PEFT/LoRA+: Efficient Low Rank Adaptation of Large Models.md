UC Berkeley

---
# Points
- Abstract
  - 기존의 LoRA에서 사용하는 adapater 행렬 A와 B는 고정된 learning rate로 업데이트된다는 점이 문제임
  - 둘 행렬의 learning rate를 조절함으로써 퍼포먼스와 학습 속도를 향상시킬 수 있는 알고리즘 LoRA+ 를 제시
- LoRA vs LoRA+
  
  <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/25504a7d-a548-4fd7-b73b-6d7d5662f281">

  - 표에 제시된 것처럼 $\lambda$는 1보다 훨씬 큰 고정된 비율임
- 🧑🏻‍💻 [LoRA+를 적용할 수 있는 코드가 있는 깃허브 링크](https://github.com/nikhil-ghosh-berkeley/loraplus)
- 논문에서는 가중치 행렬의 크기, 또는 입력 시퀀스의 길이가 커질수록 어떻게 되는지에 대한 내용을 다루고 있음.
  - 크게는 기존 LoRA가 suboptimal 할 수밖에 없는 이유에 대해 먼저 입증하고,
  - LoRA가 약점을 보이는 상황에 대해 LoRA+가 우세한 이유를 수학적으로 증명.
- 실험
  - Roberta-base, GPT-2 모델을 GLUE task로 검증
  - Llama-7b 모델을 MNLI, flan-v2 dataset으로 검증
  - 난이도가 높은 태스크에 대해서는 그 효과가 확실하지만, 상대적으로 난이도가 낮은 태스크에 대해서는 효과가 미미한 편임
---
링크: https://arxiv.org/abs/2402.12354
