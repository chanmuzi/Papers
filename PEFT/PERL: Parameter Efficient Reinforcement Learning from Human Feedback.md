Google Research

---
# Points
- 요약
  - 학습에 많은 비용이 발생하는 RLHF(Reinforcement Learning from Human Feedback)의 단점을 극복하기 위해 reward model training과 reinforcement learning에 LoRA(Low Rank Adaptation)를 적용
  - conventional 학습 기법과 비교했을 때, 학습 속도는 기존 대비 빠르면서도 성능은 기존과 유사한 수준임이 확인됨
  - 2개의 thumbs up/down preference datasets, 'Taskmaker Coffee, 'Taskmaker Ticekting'을 공개
- 아키텍쳐 이미지. Reward model에 LoRA를 적용했다는 것 말고 차이점이 없음.
  <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/979dac15-2fda-4340-8466-a1ff3e71d43f">

- 데이터셋
  - reward model 학습과 reinforcement learning에 사용됨
  1. Text Summarization: Reddit TL;DR, BOLT Message Summarization
  2. Generating Harmless Responses
  3. Generating Helpful Responses
  4. UI Automation
  5. Generating Neural Point of View Responses
  6. Taskmaker Datasets: [Taskamster Coffee](https://github.com/google-research-datasets/Taskmaster/tree/master/TM-4-2024), [Taskmaster Ticketing](https://github.com/google-research-datasets/Taskmaster/tree/master/TM-3-2020)

나머지는 전부 실험 결과를 제시하고 있는데, 일부 케이스에서는 Full Tuning보다 LoRA로 학습한 결과가 더 좋을 때가 있음.

---
링크 : https://arxiv.org/abs/2403.10704
