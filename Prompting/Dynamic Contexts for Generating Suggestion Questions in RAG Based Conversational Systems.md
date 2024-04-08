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
- Dynamic few-shot examples
  - 데이터셋에서 question, answer, suggestion question으로 이뤄진 QAS triplet으로 출발
  - 각 example을 유저의 query 기반으로 dynamically choosing
  - 이는 각 질문에 적합한 example을 추출하도록 하는 방식임 (rather than statically)
- Dynamically retrieved contexts
  - Suggestion Question Generator가 생성한 question이 답변 가능한 형태임이 보장될 수 있도록 dynamic contexts를 이용
  - 유저의 초기 쿼리를 기반으로 탐색된 4개의 dynamic contexts -> 어디에서 retrieve?
  - 이 네 개의 dynamic contexts를 바탕으로 suggestion question을 생성
- Dataset
  - 이와 같은 작업에 특화된 데이터셋은 존재하지 않기 때문에 Pamper's Baby Sleep Coach의 228개 블로그 포스트를 데이터셋으로 사용
  - 포스트의 제목은 'query', 포스트의 내용은 각 'query'에 대한 'answer' 취급
  - 228개 포스트 중에서 35개에 대해서는 직접 suggestion question을 annotate. 이 포스트들의 제목(headline)이 초기 유저의 query와의 유사도 비교 대상이 됨
  - 즉, 유저의 query가 들어오면 이를 35개의 포스팅 제목과 유사도 비교하여 문서를 가져오게 되는데, 이때 포스팅의 제목(Query), 포스팅의 내용(Answer), 생성된 question(Suggestion question)의 형태(QAS)로 반환됨
  - 기존 데이터셋 중에서 138개의 답변(포스팅의 내용)은 answer contexts가 되어 top 4 contexts 추출의 재료가 됨
  - 따라서 유저의 쿼리가 들어오면
    1) 35개의 포스팅 제목 중에서 유사도가 높은 것들을 기반으로 dynamic shot을 구성(QAS꼴로)하고,
    2) 138개의 기존 답변 중에서 4개의 context를 뽑아 1)과 합쳐준다.
    3) 합친 것을 보고 모델이 suggestion questions를 생성한다.
  - 결국 dynamic few shot을 참고하여, 4개의 context가 주어졌을 때 shot들과 유사한 형태의 suggestion question을 만들고 이것을 얼마나 잘 만들었는지 평가하는 태스크로 이해할 수 있다.
- 평가
  - Pamper's Baby Sleep Coach로부터 228개의 블로그 포스트를 이용
  - ChatGPT, GPT-4, Claude2 모델을 사용
  - Zero-Shot, Few-Shot, Dynamic Few-Shot 비교
  - 48개의 QAS(question, answer, suggestion question)에 대해 manual analysis
    <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/53bab156-c68f-45b0-99ff-8c8332e017e8">

  - GPT-4에 Dynamic 방식을 이용하는 것이 가장 선호되는 방식

---
링크: https://arxiv.org/abs/2403.11413
