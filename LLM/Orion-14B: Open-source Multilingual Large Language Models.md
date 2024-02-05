# Points
- Abstract (Technical Report)
  - multilingual large language models, Orion-14B
  - train on 2.5 trillion toknens
  - conversational applications & other specific use cases에 맞게 fine-tune
- Data
  - English & Chinese 90% 이상, Japanese & Korean 5% 이상 차지
  - 나머지는 Spansih, French, German, Arabic, ...

    <img width="500" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/00a66a0f-45ac-43bc-b8f3-80729441f70e">
  - Text normalization, Harmful contetn removal, Personal information removal, Quality filtering, Deduplication -> 데이터 품질 보장을 위한 작업
- Pretraining
  - Tokenizer

    <img width="750" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/8f666bd4-51da-4045-96db-ae1f5dbd9398">
  - Architecture
    
    <img width="750" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/517781d9-d7aa-4fce-8b11-3d28ea9e9e29">
- Fine-tuning
  - Reinforcement Learning from Human Feedback (RLHF), Direct Preference Optimization (DPO)은 future work
  - 여기서는 Supervised Fine-Tuning (SFT)
    - 공개된 데이터셋 중 잘 정제된 COIG, WildChat, OpenOrca, UltraChat 등을 사용
    - 이때 Rule-based filtering, Quality filtering, Semantic deduplication 등을 적용
- Evaluation
  - Professional Knowledge and Reasoning: C-Eval, CMMLU, MMLU, AGIEval, Gaokao, BBH
    
    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/fcac816b-9afc-4d68-b9ff-e33de891916f">
  - Language Understanding and Common Knowledge: RACE, HellaSwag, PIQA, Lambada, WSC
    
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/9cf7c9d3-eb2e-4655-acb4-6cd92f444c52">
  - Multilingual
    
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/b4e0ec07-272b-4f7e-ac4d-c87f5273484e">

    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/1cb8d537-f04a-47ca-980d-fe19eac10f5d">


  - **Korean**

    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/50ef21e0-81c7-411a-9e2e-f8bc36bb9733">
  - Fine-tuned Model Evaluation

    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/37775f69-3bc1-4b08-a15f-9ceeb2c0fa2b">

    <img width="500" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/a46b4921-525f-429f-ab02-805526339ec4">

- Extension Works
  - Orion-14B-Long
  - Orion-14B-INT4
  - Orion-14B-RAG
  - Orion-14B-PlugIn

---
링크: https://arxiv.org/abs/2401.12246
