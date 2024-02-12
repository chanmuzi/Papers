# Points
- Abstract
  - retrieval & self-reflecion을 통해 LM의 퀄리티와 사실성을 높이는 **Self-Reflective Retrieval-Augmented Generation (SELF-RAG)**
  - reflection tokens라는 스페셜 토큰을 사용
  - LLaMA 기반 7B, 13B 파라미터로 SoTA급 LLM 이상의 성능을 보이기도 함
  - Open-domain QA, long-form generation 등의 태스크에서 성능을 검증
- 문제 정의
  - 기존 RAG 시스템들은 'indiscriminately regardless of whether the factual grounding is helpful'
  - 즉, retrieval 대상이 실제 generation에 도움이 될지 안될지와 상관 없이 문서를 가져온다는 것이 문제점
  - 따라서 retrieval이 필요한지 먼저 따진 뒤, 실제로 retrieved된 documents를 바탕으로 생성된 결과를 평가(criticize)
- Method
  - 파이프라인 이미지 (좌: 기존 RAG, 우: Self-RAG)
    <img width="1200" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/0d37a919-e5e4-439d-91a5-33e72d45f9b5">

  - 입력($x,y_{< t}$)이 주어지면 Retreive가 필요할지를 먼저 결정
    - 필요하다고 결정된 경우 'Retrieve, Generate, Critique' 세 단 계를 거침
    - 이때 생성된 세 개의 스페셜 토큰 'IsRel, IsSup, IsUse'를 바탕으로 $y_{t}$에 대해 평가를 내림
    - 필요하지 않다고 결정된 경우 $y_{t}$를 직접 생성하고 바로 'IsUse' 토큰에 대한 예측 수행
  - $y_{t} \in y$에 대해서 각 스텝마다 critic model $C$를 학습시킴
    - 추론할 때는 retrieved text chunk에 마스크를 씌워줌

  - 알고리즘 이미지
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/a921a36a-4b90-4f25-9f10-412d8c9a052a">

  - 스페셜 토큰 정의
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/6361194a-6882-4462-af78-c57557ed649d">

- 관련 연구
  - Retrieval-Augmented Generation
  - Training and generating with critics: RLHF, PPO


---
링크: https://arxiv.org/abs/2310.11511
