# Points
- queries에 관계 없이 다양한 태스크를 잘 처리하는 모델을 만드는 것이 목표
- 이를 위해 LM이 복잡한 문제를 작은 것을 쪼개어 처리할 수 있도록 하는 meta-prompting 방식을 적용
  - 여러 inquiries를 독립적으로 처리하고 그 결과를 synthesize
  - Meta Model이라고 부르는 메인 모델이 존재: 여러 악기를 다루는 '지휘자'로 비유
  - 매 iteration마다 필요한 expert를 call하여 결과를 취합하는 방식
   <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/8c674d55-ee23-4098-a1d8-5eeb8edc4ade">

- 추가적으로 LM에 내재된 critical thinking & robust verification process를 사용
- Python interpreter와 같은 외부 tool과도 통합 가능함을 입증
- Game of 24, Checkmate-in-One, Python Programming Puzzels와 같은 태스크에 대해 GPT-4로 검증
  - Standard prompting, Zero-shot CoT Prompting, Expert prompting, Multi-persona prompting (SPP) 등과 비교
  - 태스크에 따라 Exact Match (EM), Soft Match (SM), Functionally Correct (FC) 등을 metric으로 사용
  - GPT-4 (gpt-4-32k), GPT-3.5 (gpt-35-turbo) through Microsoft's Azure OpenAI Service
- Meta Model의 시스템 메시지
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/0c90aa70-f2bc-40d1-bf58-dbc79f4fcc6b">

- 관련 연구
  - Enhancing Reasoning in Language Models through Prompting: 각종 프롬프트 관련 연구 목록
  - Iterative Self-Feedback and Refinement Mechanisms
  - Exploring Role-Playing in Language Models
  - Autonomous Decision-Making and Execution in Multi-Agent LM Systems


---
링크: https://arxiv.org/abs/2401.12954
