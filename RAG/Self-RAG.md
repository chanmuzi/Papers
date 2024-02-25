[ICLR 2024] AI2

---
# Points
- Abstract
  - Self-Reflective Retrieval-Augmented Generation (Self-RAG): through retrieval and self-reflection
  - 필요에 따라 passage를 탐색하고, 이를 바탕으로 결과물을 생성하며 _reflection tokens_ 를 reflect하는 방식
  - 하나의 arbitrary LM을 학습시키는 프레임워크
- Overview of Self-RAG
  <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/3c370882-dabf-4bff-b838-6ac9baec8852">

- 관련 연구
  - Retrieval-Augmented Generation: LM의 input sapce를 retrieved text passages로 확장
  - Concurrent RAG work: natural language inference model, summarization model
  - Training and generating with critics: Proximal Policy Optimization (PPO), Reinforcement Learning from Human Feedback (RLHF)
- Self-RAG
  - 최종 정답을 $y$라고 할 때, 입력 $x$와 이전까지 생성된 $y_{< t}$를 바탕으로 retrieve가 필요할지를 판단. 이때 사용되는 것이 $Retrieve$ 스페셜 토큰
  - $Critique$ 토큰은 크게 세 가지로 구성됨: $IsRel, IsSup, IsUse$
  - retrieve가 필요한 경우, 위 세 개의 critique 토큰으로 부터 얻은 결과를 weighted sum하여 $y_{t}$에 대한 최종 rank를 결정
  - 스페셜 토큰에 따른 각 output 후보들과 메커니즘을 정리한 pseudo algorithm 이미지는 아래를 참조
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/ee863300-58e9-4296-b2ae-5f2123955035">

    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/a7b34b05-63a8-44dc-89be-c1a4accc8c6f">

- Dataset
  - PubHealth, ARC-Challenge
  - PopQA, Trivia-QA-ufiltered
  - ALCE-ASQA: FactScore
  - Llama2-7B/13B, Alpaca-7B/13B, CoVE-65B 등 모델로 평가
 
---
링크: https://arxiv.org/abs/2310.11511
