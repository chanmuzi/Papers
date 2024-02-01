# Points
- Information Retrieval에 활용되는 RAG 시스템을 평가
  - prompt, document position, context에 포함되는 문서 숫자 등을 다양하게 바꿔보면서 결과를 확인
  - 기존 가정과 달리 무관한 문서(노이즈)를 포함시키는 경우 정확도가 약 30% 향상하는 케이스가 있는 것으로 확인됨
- Keywords
  - RAG, LLM, Information Retrieval
  - Generative Language Models, Information Retrieval, Retrieve and Generate (Related Work)
- Open-Domain Question Answering
  - ODQA에서 활용되는 주요 개념을 간단히 설명
  - Retriever, Reasoner
- Documnet의 종류를 query와의 관계에 따라 크게 네 가지로 구분
  - Gold: original NQ 데이터셋에서 질문과 contextually relevant 하면서도 정답을 포함하는 위키피디아 페이지
  - Relevant: Gold와 거의 유사. 정답에 대한 추가적인 정보를 제공
  - Related: query와 관련성은 높지만 정답을 포함하고 있지는 않음
  - Irrelevant: query와 관련성도 낮고 정답도 포함하지 않음
- Results
  - 일반적으로 gold document가 query와 가까이 배치되는 것이 가장 좋음(Near > Mid > Far)
  - query와 관련성이 높은 문서들을 추가한다고 하더라도 모델의 정확도가 향상되지 않고 오히려 떨어지는 경향
    <img width="1079" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/a2262ebb-4a6b-4336-8a4c-b787e104914d">
    
  - query와 관련성이 낮은 문서(Noise)를 추가하는 것이 오히려 모델의 정확도를 향상시키는 데 도움이 됨
    <img width="950" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/d2df31e2-6dc6-414e-9adc-f560aa34c6a6">

  - 그런다고 해서 당연히 무관한 문서들만으로 query 앞을 채우라는 뜻은 아님. 최소한의 (query와의) 관련성 높은 문서들이 필요하긴 함

---
링크: https://arxiv.org/abs/2401.14887
