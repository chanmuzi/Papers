# Points
- Abstract
  - self-knowledge에 대한 중요도가 높아지고 있음
  - 다섯 개 카테고리의 unanswerable/answerable questions로 구성된 dataset, SelfAware를 공개
  - GPT-3, InstructGPT, LLaMA 등 20여 개의 LLMs으로 실험을 수행
  - in-context learning & instruction tuning이 self-knowledge를 강화할 수 있음을 확인
  - "Do large language models know what they don't know?"
- Know-Unknow Quadrant
  
  <img width="350" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/61187359-8d74-4c6e-bb25-820e4f8c5c83">

- Dataset
  - Unaswerable questions: Quora, HowSutffWorks와 같은 온라인 플랫폼에서 2,858개 수집
  - 최종적으로 1,032개의 unanswerable questions
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/88abb8af-0e06-49d8-9883-8c68f919bb6b">

  - SQuAD, HotpotQA, TriviaQA로부터 answerable questions를 추출
  - 총 2,337개의 answerable questions
- Method
  - 유사도 측정 함수 $f_{sim}$: 문장 $t$와 reference $U={u_{1},u_{2},...,u_{n}}$ 사이의 유사도
    $$S_{i} = f_{sim}(t,u_{i})$$

  - LLM의 self-knowledge는 F1 score로 측정
- Experiment
  - Models: GPT-3, InstructGPT, LLaMA, Alpaca, Vicuna
  - Methods: Direct, Instruction, In-Context Learning (ICL)
  - Results
    <img width="900" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/1dc24b6c-7ad8-4cb4-9175-370495b8ebde">

    - 모델 파라미터 사이즈에 F1 score가 비례하는 경향
    - Instruction Tuning이 self-knowledge를 향상시키는 데 큰 도움을 줌
    - (ICL에서 주어지는) Provided examples도 self-knowledge 향상에 도움을 주는 것으로 확인
---
링크: https://arxiv.org/abs/2305.18153
