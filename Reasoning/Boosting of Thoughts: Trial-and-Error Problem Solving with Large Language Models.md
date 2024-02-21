# Points
- 여러 trial-and-erro reasoning 경험을 통합하기 위해 trees of thoughts를 반복적으로 활용하는 프레임워크
- GPT-4 & Llama2로 mathematical problems(GMS8K, AQuA)에 대해 BoT (Boosting of Thoughts) 성능을 평가
- 아키텍쳐
  <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/52b82ab1-a6f5-4812-be8b-c4bb3222f6d1">
  
  <img width="900" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/e8fe8448-dc87-452a-9897-c9c1a8aa9724">

  - prompt를 바탕으로 Thought Structures Generation(1)에서 대량의 tree thought structures를 생성
  - Thought Structures Aggregation(2)에서 (1) 생성 결과물을 thought chain $\bar{z}_{1...n}$를 생성
  - thought chain은 (3)에서 더 나은 프롬프트를 만들기 위해 _experience_ 생성에 활용됨

- 관련 연구
  - Multi-Step Reasoning, Automatic Prompting, Prompt Engineering via Feedback


---
링크: https://arxiv.org/abs/2402.11140
