Tsinghua University, Microsoft

---
# Points
- 요약
  - 언어 모델이 학습하는 모든 토큰의 중요도가 같지 않을 것이라는 전제
  - 더 높은 excess loss를 지닌 토큰에 대해 focused loss를 적용하는 Selective Language Modeling(SLM)을 제안
- SLM 아키텍쳐 이미지
  
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/7dd2b0e3-7829-4eb8-b3d8-d4bb39de53ee">

- Selective Language Modeling (SLM)
  - Not All Tokens Are Equal: Training Dynamics of Token Loss
    - 개별 토큰에 대한 loss가 학습 동안 어떻게 변화하는지 확인
    - 제대로 학습된, 즉 loss가 높았었는데 낮아진 케이스(H->L)는 전체의 26%에 불과함
    - 따라서 학습을 진행했을 때 효과를 볼 수 있는 토큰에 집중하도록 만드는 것이 본 modeling의 목표임
  - Method
    1. reference model을 high-quality data에 대해 학습
    2. reference model을 사용하여 corpus 내 각 토큰의 loss를 계산
    3. reference loss와 비교하여 higher excess loss를 갖는 토큰들을 선별하여 모델을 학습
   
    - 이때 선별은 전체 토큰의 k%만큼 수행하는데, 다음과 같이 표시함. ($I$는 loss가 excess loss에 해당하면 1, 그렇지 않으면 0 값을 가짐)
      
      <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c2a553ed-3c04-410d-8ad0-435c48c646f5">

    
  - Method image
    
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/786645f7-1e79-48a0-83a0-ad3a4de0705b">

- Models
  - Tinyllama, Phi-1.5, Qwen1.5, Gemma, DeepSeekLLM, DeepSeekMath, Llema, Mistral
- Datasets
  - OpenWebMath (OWM), StarCoderData
- Results

  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/15be2863-e7d9-474b-9c09-5b53345c2252">

  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/ea720101-cd01-468c-8f66-a08efc967a6b">

  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/9e5e2e2e-42ed-4cf9-b092-ac77fc7d5928">

---
링크: https://arxiv.org/abs/2404.07965
