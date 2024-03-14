WWW'24, May 13-17, 2024, Singapore, Singapore

---
# Points
- Abs
  - retrieve-then-read, generate-then-read 패러다임 둘 다 LLM을 이용하지만 근거에 대한 다양한 요구 사항을 처리하지는 못함
  - ODQA를 세 가지 스텝으로 처리하는 framework, LLMQA를 제안
    - (1) query expansion (2) document selection (3) answer generation
  - LLM이 generator, rernaker, evaluator 역할을 수행할 수 있도록 instruct
  - role-playing prompt를 refine할 수 있는 prompt opitmization 알고리즘을 제안
- Related Work
  - Open-Domain Question Answering: Retrieve-then-read paradigm, Generate-then-read paradigm
  - Capabilities: Generation capability of LLMs, Ranking capability of LLMs, Evaluation capability of LLMs
  - Prompt Optimization
- Method
  1. Query Expansion: LLM을 generator로 사용하여 context를 이해하고 query를 재가공
  2. Document Selection: 적절한 문서를 찾기 위해 두 가지 단계를 거침
      - Coarse-grained retrieval of top-n documents, Fine-grained reranking of top-k documents from n can-didate
      - LLM이 document reranker 역할을 수행하도록instruct. top-k개의 문서를 추가 screening
  3. Answer Generation
      - LLM 기반의 reader $G_{a}$ 를 이용하여 정확하고 신뢰 가능한 response를 생성

- 전체 파이프라인 이미지
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/7ddcea46-c782-4cbe-b9e6-87b6b3d02274">


---
링크: https://arxiv.org/abs/2403.05217
