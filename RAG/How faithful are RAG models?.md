Stanford University

---
# Points
- 요약
  - LLM이 지닌 내부 지식(internal prior로 표현)과 retrieved information이 불일치하는 상황이 대한 연구
  - internal prior가 weak한 경우 modified information을 제공하면 retrieve information을 적극적으로 활용하고, internal prior가 strong한 경우는 반대임.
  - 즉, LLM이 retrieved infromation을 따를 가능성은 모델이 context 없이 생성한 답변에 대해 갖는 confidence(prior probability)에 반비례함
- 모델
  - gpt-4-turbo-preview, gpt-3.5-turbo-0125, mistral-instruct-v0.1
  - 논문의 실험 결과는 gpt-4에 대한 것이고, 나머지 두 개는 appendix에서 다룸
- 데이터셋
  - Drug Dosages, Sports Statistics, News, Dates, Names, Cities
- 평가 분석 방법
  - context를 참고하지 않았을 때의 답변과 참고했을 때의 답변이 동일한 경우, 모델이 prior를 선호하는 것으로 판단
  - 반대로 retrieved information이 정답과 align하는 경우, 모델이 RAG를 선호하는 것으로 판단
- 예시 결과표
  
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/9ebc2dc1-6413-4742-9abd-1e0055e0a509">

  - 숫자를 계산해야 하는 태스크에서 값에 곱셈 또는 덧셈을 적용하거나 고유 명사를 변형하는 등의 방식을 통해 prior에 대한 RAG 선호도를 파악한 결과
- 프롬프트 비교

  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c769e895-c415-462f-87db-0a01ffc01c63">

  - strict prompt를 사용할 때 standard prompt 대비 RAG를 선호할 가능성이 일관되게 높은 것으로 확인됨
---
링크: https://arxiv.org/abs/2404.10198
