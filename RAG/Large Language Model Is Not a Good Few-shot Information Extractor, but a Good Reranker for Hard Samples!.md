# Points
- 기존과 같이 LLM을 few-shot information extractor로 활용하는 것이 그다지 효율적이지 않다는 지적
  - fine-tuned SLM 대비 비용이 많이 발생
  - latency가 너무 높음
- 적절한 프롬프트 전략을 활용하여 SLM의 단점을 보완하겠다는 취지
  - 이때 활용되는 방식을 **adaptive _filter-then-rerank_ paradigm**이라고 부른다.
  - SLM을 filter로 LLM을 reranker로 사용하게 됨
- LLM과 SLM의 성능을 비교
  - NER, RE, ED (Event Detection), EAE (Event Argument Extraction)
  - SLM이 일반적으로 effective (LLM이 뛰어난 것은 오히려 제한적인 상황)
    <img width="853" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/e267fa24-e914-40ca-b97e-36128a3a3607">

  - LLM 사이에서도 패턴이 그다지 일관적이지는 않기도 하고, inference 속도가 너무 느리다는 문제가 존재함
    <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/de7f9ae0-a6f7-4b90-b49e-bfa92b9e4d45">
- LLMs are Good Few-shot Reranker
  - SLM으로 top-N개의 후보 label을 고르고 이에 대해 LLM이 판단. LLM이 sentence에서 sample 수준으로 focus를 옮긴다고 표현함
  - 의외로 결과가 안좋았는데, hard sample에 대해 더 적합할 것이라고 추측하고 실험을 진행했고 그 예상이 맞았음
  <img width="480" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/52a7030c-11ca-4d81-b852-a1f8ff1a83e5">

- Method
  - supervsied SLM을 필터로 사용하여 preliminary decisions를 생성
  - confidence score가 일정 threshold를 넘어가는 것만 sampling
  - 쉬운 sample에 대해서는 SLM의 최종 결과를 보유, 어려운 sample에 대해서는 LLM을 reranker로 사용
  - 여기에서는 MCQ 프롬프트가 사용됨. 최종 결과는 LLM이 생성하게 됨
    <img width="402" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/b10625df-83de-4e73-b42f-2d5d2915ad45">

---
링크: https://arxiv.org/abs/2303.08559
