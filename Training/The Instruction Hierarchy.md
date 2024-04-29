OpenAI

---
# Points
- 요약
  - 언어 모델이 서로 다른 우선순위를 갖는 instruction을 어떻게 처리할 것인지를 정의한 instruction hierarchy를 제안
  - LLM이 낮은 우선순위를 갖는 instruction을 무시할 수 있도록 하는 automated data genearation을 제안
- 배경
  - direct/indirect prompt injection attack, jailbreak, system prompt extraction 등 언어 모델에 대한 adversarial attack(적대적 공격)이 중요한 이슈로 떠오름
  - 그러나 system message와 user message 간의 구분, 우선순위에 대한 연구는 부족.
  - 따라서 LLM이 instruction 간의 우선순위를 구분하여 지시를 따를 수 있도록 하는 연구를 제안
- 우선순위 구분 이미지 (ChatGPT 대화 기준)
  
  <img width="750" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/5c6ca40f-8083-45f9-9e63-50930cd42409">

- The Instruction Hierarchy
  - Overview of Ideal Model Behavior
    - Aligned: system message와 user message, 그리고 tool output이 동일한 경우
    - Misaligned: system message와 user message, 또는 tool output이 상충되는 경우. 이때는 유저의 instruction을 무시하거나 거절할 필요가 있음
  - Training Data Generation for Different Attacks
    - Context Synthesis: request를 구성하고 이를 작은 조각들로 쪼개어 aligned instruction을 위한 데이터를 생성.
    - Context Ignorance: misalgined instruction을 위한 데이터를 생성. lower-level instruction을 본 적이 없다면 무시하고 원래 답변을 생성하도록 학습.
    - 단, 모델이 무조건적으로 거절하지 않을 수 있도록 학습하는 것이 중요.
- Results
  - Main results
    
    <img width="750" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/0f938032-2412-43ed-ad86-31bf7a48eaae">

  - Generalization results

    <img width="750" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/b7544a41-bf44-418f-a93f-6f4abd7160bd">

  - Overrefusla results

    <img width="750" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/ebdc1a94-14a8-433d-95ed-c03cf3058071">

---
링크: https://arxiv.org/abs/2404.13208
