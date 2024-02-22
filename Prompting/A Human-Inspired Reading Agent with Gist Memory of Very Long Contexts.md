Google DeepMind

---
# Points
- Abstract
  - context length를 최대 20배까지 늘릴 수 있는 LLM agent system, ReadAgent를 제안
  - 단순한 prompting system으로 (1) Episode Pagination (2) Gisting (3) Lookup 의 단계를 거침
  - 핵심은 긴 텍스트를 잘라서 gist memory 형태로 저장하고 이를 기반으로 답변에 필요한 문서를 참조하게 된다는 것
  - 아래는 프로세스를 간단히 보여주는 이미지
    
    <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/51efd6ea-f2d2-4f49-8944-11186a448dc9">

- 관련 연구
  - Long-Context LLMs, Retrieval, LLM Agents for Long Texts
- Gist Memory
  1. Episode Pagination: 모델에게 paragraph들을 제시하고 어디에서 내용을 끊어 'page'로 만들지를 결정하게 함
     <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/e3afa63f-c8bf-43bf-821b-70031e9b6586">

  2. Memory Gisting: 각 페이지마다의 내용을 간단히 정리하여 GIST로 만들고 그 결과물들을 concatenate. 이를 이후 '탐색의 근거'로 활용.
     
     <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/6dfbb951-ed3c-4308-8f1e-090f16f1763c">

  3. Look-Up
    - ReadAgent-P: 모델이 여러 개의 pages를 하나의 prompt 내에서 parallel하게 참고하여 답변을 생성
      <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/5230d708-a3a5-4bbc-b82d-6b07e7c00782">

    - ReadAgent-S: 한 번에 한 개의 page를 참고하여 답변을 생성하되 이 과정을 최대 횟수까지 반복
      <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/63c061c0-7d0f-4d34-a6ea-99375bad35c0">

- Experiments
  - QuALITY, NarrativeQA, QMSum 데이터셋에 대해 실험
  - instruction-tuned PaLM 2-L 모델을 활용. GPT-3.5로도 실험한 결과가 있음.
  - Compression Rate (CR)을 지표로 사용. $CR = 100 * (1-\frac{word-count(in-context}{word-count(full-context text})$
  - QuALITY
    
    <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/5fa721c6-ae0e-4cb5-9a01-a178980f23ba">

  - NarrativeQA
    
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/4cc48f24-897e-4405-bb17-bb49946f1779">

  - QMSum validation
    
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/208b46c0-411b-4695-a865-02ba0f4f89f6">

---
링크: https://arxiv.org/abs/2402.09727
