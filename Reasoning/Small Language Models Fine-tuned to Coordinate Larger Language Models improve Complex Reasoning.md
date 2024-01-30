# Points
- DaSLaM, 복잡한 문제를 subproblems로 쪼갤 수 있는 decomposition generator
  - 13B (상대적으로 작은 모델)을 decomposition generator로 사용하여 policy gradient optimization을 수행
  - (Blackbox라고 여겨지는) solver LM과 interact, 여기서는 175B text-davinci-003로 실험
  - GPT-3.5를 능가하고 GPT-4에 견줄 만한 성능
- 아키텍쳐 이미지
  <img width="1400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/66ef13bc-a7fc-40d6-be0c-cc262a0305e6">

- MATH, AQuA, JEEBench 벤치마크로 성능 확인
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c1b341b5-7820-44ca-b16f-ced87c22e374">
  
  <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/7bbe6603-a5ee-4f70-a155-dcd99f94fafd">

- 관련 연구
  - Cot prompting, Decomposing, Hint Prompting
- Learning to Decompose from Feedback
  - policy network, environment, state and action space 등 강화학습 관련 개념들을 바탕으로 decomposition을 수행
  - PPO setup

---
링크: https://arxiv.org/abs/2310.18338
