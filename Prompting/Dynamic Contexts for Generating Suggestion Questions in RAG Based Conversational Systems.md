University of Illinois, Chicago

---
# Points
- 요약
  - RAG 기반 대화형 agent를 사용할 때, 이 system의 능력과 한계에 대해 정확히 인지하지 못하는 사용자들은 명확한 질문을 하기가 어려움
  - suggestion question generator를 개발. dynamic few-shot example과 dynamic retrieved context를 이용.
- 아키텍쳐 이미지
  <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c4101adb-68f0-4509-9f2f-538841944949">

- 관련 연구
  - Clarification questions: AmbigQA, CLAQUA, CLAM, ISEEQ, CLARIT 등
- 컨셉
  - dynamically retrieved contexts는 네 개의 dynamic contexts로 구성. 유저 쿼리를 기반으로 retrieve.
  - OpenAI Embeddings을 이용하여 example과 query를 임베딩. 코사인 유사도를 활용
- 평가
  - Pamper's Baby Sleep Coach로부터 228개의 블로그 포스트를 이용
  - ChatGPT, GPT-4, Claude2 모델을 사용
  - Zero-Shot, Few-Shot, Dynamic Few-Shot 비교
  - 48개의 QAS(question, answer, suggestion question)에 대해 manual analysis
    <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/53bab156-c68f-45b0-99ff-8c8332e017e8">

  - GPT-4에 Dynamic 방식을 이용하는 것이 가장 선호되는 방식

---
링크: https://arxiv.org/abs/2403.11413
