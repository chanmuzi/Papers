# Points
- SFT와 같이 annotated 데이터가 필요하지 않은 새로운 fine-tuning 방식 Self-Play fIne-tuNing (SPIN)을 제시
  - LLM이 이전 iteration으로부터 학습 데이터를 스스로 생성하고, 이에 대한 policy를 스스로 개선하는 방식
  - GPT-4의 preference data로 DPO를 적용한 모델보다 뛰어난 성능을 HuggingFace Open LLM Leaderboard에서 입증
- 관련 연구 중 Synthetic Data를 들 수 있는데, 다른 연구와 달리 target model 스스로가 synthetic 데이터를 생성한다는 방법이 독특함
- Curriculum Learning
  - 난이도가 낮은 것부터 학습하는 방식으로 데이터의 난이도를 잘 설정해야 의미가 있음
- Method
  - two-player 게임을 진행하는데, 한 쪽은 response를 사람이 만든 것인지 LLM이 만든 것인지를 판별. 반대편은 사람의 response와 구분이 어려운 것을 생성 (GAN..?)
  - 이때 two player가 같은 LLM이지만 difference iterations에 해당함
  - 따라서 차이를 구분해야 하는 main player와 헷갈리게 하는 문장을 생성하는 opponent player의 학습 목표가 다름
- Experiments
  - zephyr-7b-sft-full 모델
    <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/bf1dba31-c08d-424b-a51a-84c3c499630d">

  - DPO와의 비교: iter-1부터 DPO보다 뛰어난 성능이 나타남
    <img width="780" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/fddb48d0-ca37-4799-9186-534f8d209e1d">

  - few-shot setting
 
    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/1286dcac-1b83-4373-b8e5-36f1e5ee0ef7">



---
링크: https://arxiv.org/abs/2401.01335
