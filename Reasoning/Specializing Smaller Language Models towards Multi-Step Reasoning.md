# Points
- Abstract
  - GPT-3.5와 같이 굉장히 큰 모델로부터 distill해서 특정 태스크에 강한 작은 모델을 만들자
  - 언어 모델의 multi-dimensional abilities 간의 tradeoff를 보여줌
  - 10B 이하의 작은 모델들이 multi-step math reasoning ability에 있어서 보였던 scaling curve를 들어 올리는 결과를 보여줌. 즉, 작은 모델도 가능성 있다!
- 관련 키워드
  - Large Laguage Model's Abilities
  - Specialized Language Models
  - Distillation and Data Augmentation
- 컨셉
  - Distillation from Code-Davinci-002
    - code-davinci-002로부터 생성된 데이터로 smaller Flan-T5를 학습
    - API는 토큰별 확률을 5개까지만 제공하므로 5개를 활용하고 나머지 토큰들에 대한 확률은 0으로 취급
  - 데이터셋: GSM8K, BigBench Hard를 사용 / MultiArith, ASDiv, SVAMP는 OOD(Out of Distribution) 검증용으로 사용
  - GPT-3.5와 Flan-T5 모델 간의 tokenizer가 다르다는 문제점을 'dynamic programming'으로 해결
    ![image](https://github.com/chanmuzi/Papers/assets/101971295/6af96171-6baa-4ab4-a3c5-3d5183af91ab)

- 결과
  ![image](https://github.com/chanmuzi/Papers/assets/101971295/dde0e378-ac22-4a8a-83d7-0dd46eeaee4f)

  ![image](https://github.com/chanmuzi/Papers/assets/101971295/86b792fa-2967-4e9a-94c6-3bcb41c049d6)

  ![image](https://github.com/chanmuzi/Papers/assets/101971295/fca52408-4a37-48dc-831e-54740dc40c36)

---
링크: https://arxiv.org/abs/2301.12726
