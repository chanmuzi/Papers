Brown University

---
# Points
- Abstract
  - unannotated text를 instruction tuning을 위한 task-specific training datsets으로 변환해주는 오픈 소스 모델
  - 위와 같은 태스크를 **conditional task generation** 이라고 표현함. 이렇게 생성한 데이터셋으로 모델을 학습하여 zero-shot tasks dapatation 능력을 높임
  - 1.65M 개의 examples로 학습한 LLM, Bonito.
  - yes-no question answering, extractive question answering, natrua langauge inference (NLI)
- Bonito 아키텍쳐 이미지
  <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/98b4b6e8-6a9b-4dbf-b4f2-560c6417890f">

- 관련 연구
  - Zero-Shot Task Adaptation
  - Instruction Tuning
  - Domain Adaptation
  - Task Generation
  - Knowledge Distillaion
  - Question Generation
- Bonito: Learning to Generate Tasks
  - Conditional Task Generation with Attributes (CTGA): 속성(attribute)를 바탕으로 conditional task generation을 위한 학습용 데이터셋 (1.65M)
  - input-output pair 예시 이미지
    
    <img width="350" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/94b9865e-075b-4c04-90cd-428dde47c8bd">

  - Mistral-7B 모델을 CTGA 데이터셋에 fine-tuning (Q-LoRA)
- Experiments
  - Baselines: None, TAPT (Taks-Adaptive Pre-Training)
  - Models: Mistral-7B, Llama 2 7B
  - Evaluation: F1 score, ranked classification, SQuAD F1 score
  - Adaptvie Instruction Tuned Models: Mistral-7B-Instruct-v0.2
- 실험 결과 (도표)
  - Mistral > Llama2
  - Instruct 모델 > base 모델
  - task special은 Extractive QA에서는 열세 (SQuAD 데이터셋이 문제의 원인일 것으로 추정)
    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/3f027988-cd08-4f0a-824c-98f31d1e2bde">

    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/4aa83b47-0175-45bf-bee9-0a7a23859cdd">

    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/cfd20393-90e7-4f49-8076-8c399ee65928">


---
링크: https://arxiv.org/abs/2402.18334
