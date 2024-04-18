KAIST AI

---
# Points
- 아키텍쳐 이미지
  
  <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c08b7800-84b9-41b3-8e89-ce7524dc538d">

- 관련 연구 키워드
  - Mathematical Reasoning of LLMs
  - Step-level Supervision
  - Self-Training for Mathematical Reasoning
- 사전 지식
  - Rejection Sampling Fine-Tuning (RFT) - [Yuan et al., 2023](https://arxiv.org/abs/2308.01825)
  - Direct Preference Optimization (DPO)
- Method
  - Self-Training with Outcome Supervision
    - 초기의 human-curated dataset $D$를 이용하여 학습 모델이 스스로 데이터를 생성
    - $D_{\mathrm{RFT}}$으로부터 correct solution $\hat {y_{i,j}}$를 고르고, $D_{\mathrm{GEN}}$으로부터 incorrect solution $\hat {y_{i,k}}$를 골라서 pair를 생성
    - 이때 둘 사이의 편집 거리(edit distance)는 최대가 되도록 pair를 구성
  - Multi-Step Preference Learning
    
    <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/92987927-a6fb-4b2d-8a89-1c19b9a8677c">

    <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/79109b98-3a49-45bb-bc47-9d92990eabc3">

    - 원래 preference를 학습시킬 때는 첫 번째 이미지에 나타난 수식을 따라서 학습을 진행. 그러나 처음 실수가 발생한 "pit"만을 문제로 인식하는 두 번째 이미지의 수식을 따른 것이 본 논문의 방식임
    - 왜냐하면 해당 실수 이후의 논리들은 잘못된 내용을 기준으로 정확할 수 있기 때문임. 따라서 여기에 페널티를 부여하지 않고 0으로 처리한다는 것을 알 수 있음.
  - Self-Explore
    - 모델을 self-guided explorer로 사용. 이는 여러 step으로 쪼갠 과정들 중 어떤 것이 "pit"에 해당하는지를 파악하는 데 사용됨.
- Datasets and Models
  - GSM8K, MATH
  - Mistral-7B, Llemma-7B, Deepseek-Math-7B-Base
---
링크: https://arxiv.org/abs/2404.10346 
