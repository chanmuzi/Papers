# Points
- Abstract
  - LLM 기반의 NLG (Natural Language Generation) 평가 방법에 대한 taxonomy(분류 체계)를 제공
  - humna-LLM collaboration 방식에 대해서도 다룸
  - 이러한 방식의 문제점과 향후 발전 방향에 대한 논의
 

## 1. LLM-derived Metrics
  - (1) Embedding-based Metrics
    - 기존 모델들 중에는 BERTScore 또는 BARTScore 포지션에 해당
    - 언어 모델이 reference와 targe 텍스트 간의 semantic similarity를 계산해야 함
    - 최근에는 text-embedding-ada-002 모델 등이 사용됨
  - (2) Probability-based Metrics
    - GPT Score, DELTAScore, GPT-3.5 (text-davinci-003) 등 logits을 활용
  - Pros and Cons
    - 모델의 평가 결과가 human judgements와 잘 일치 (장)
    - robust하지 않고 efficiency가 부족하다는 단점. LLM을 사용하기 위해서는 시간과 자원이 많이 필요. (단)
    - closed-source LLMs는 활용하기 더욱 어려움 (단)
    - 게다가 인종, 성별, 지역, 외모, 나이, 재정 상태 등에 관한 social bias 문제 (단)
## 2. Prompting LLMs
  - 사람의 평가를 gold standard로 보던 견해에서 탈피
  - (1) Evaluation Methods
    - GPT-3.5 & GPT-4로 human label을 대체
  - (2) Comparison
    - 두 문장 중에 더 나은 것을 고르는 비교 방식
    - medium-sized LLM (FlanT5, LLaMA-2) 등이 활용
  - (3) Ranking
    - 여러 개가 주어지면 한 번에 랭킹을 매기는 방식
  - (4) Boolean QA
    - LLM이 질문에 대해 Yes 또는 No로 대답하게끔 하는 방식
  - (5) Error Analysis
    - 번역에 에러가 존재하는 span을 탐지하도록 하는 방식
  - form and requirements, analysis and explanations, demonstarations 등을 지정해 주어야 함
  - source document & target text는 task에 따라 다름
  - 사람이 평가했던 것을 예시로 삼아 평가
  - 역할을 지정해주기도 함
  - Pros and Cons
    - 평가 방식이나 기준을 자연어로 편하게 지정할 수 있어 flexibility 높음 (장)
    - 평가 결과에 대한 설명을 생성할 수 있어서 설명력(interpretable)이 높아짐 (장)
    - 사람의 평가에 준하는 SoTA 급 결과 (장)
    - position bias (단)
    - verbose responses를 선호하는 경향 (단)
    - non-Latin 언어에 대한 점수가 낮게 나오는 경향 (bias) (단)
   
## 3. Fine-tuning LLMs
  -  상대적으로 작고 가벼운 모델을 fine-tuning하여 평가에 활용. 이를 위해 고품질의 데이터셋을 구축할 필요가 있음
  -  Data Construction
      -  다양한 LLM으로부터 생성된 텍스트를 target으로 삼는 경우도 존재
      -  instruction을 구축하는 것이 메인 과제
  -  PandaLM, TIGERScore, AUTO-J
  -  LLaMA와 같은 오픈 소스 모델을 사용하여 fine-tuning
  -  Pros and Cons
      -  low-cost inference, good reproducibility, performance close to GP4 (장)
      -  prevent biases (장)
      -  지금까지의 연구는 대부분 LLaMA 위주 (단)
      -  반복적인 fine-tuning은 결국 computational expenses를 발생 (단)
## 4. Human-LLM Collaborative Evaluation
  - 평가하기 어려운 domain에 대해서 더 강건한 결과를 도출하기 위한 방법으로 제시
  - COEVAL
  - Broader Evaluation Tasks
    - 모델을 testing and debugging하는 것도 NLG 평가에 포함됨
    - 모델이 생성한 critiques를 평가에 활용
  - Pros and Cons
    - efficiency와 cost 사이의 적절한 균형 (장)
    - LLM이 format에 너무 민감 (단)
    - prompt writing을 추가적으로 해야 함 (단)
    - 결국 사람이 일정 수준 개입해야 함 (단)


---
링크: https://arxiv.org/abs/2402.01383
