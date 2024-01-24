# Points
- mistake finding & output correction
- release [BIG-Bench Mistake](https://github.com/WHGTyen/BIG-Bench-Mistake): a dataset of **logical mistakes in Chain-of-Thought reasoning traces**
  - 2186개. BIG-bench의 5개 태스크로부터 생성
  <img width="886" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/8407e55c-3860-4d31-8a55-f4df39f87822">
  
  - mistake annotation을 포함하고 있는 데이터셋 중 하나는 [PRM800K(Let's Verify Step by Step)](https://arxiv.org/abs/2305.20050) 가 있다. 이는 올림피아드 수준의 수학 문제를 포함하는 데이터셋이다.
- LLMs은 일반적으로 logical mistakes를 잘 찾지 못한다.
- **backtracking method**는 실수에 대한 위치 정보가 주어졌을 때 성능을 크게 개선할 수 있는 방법이다. 저자는 이를 'verbal reinforcement learning'으로 이해한다고 밝혔다.
  <img width="959" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/90b00b49-d9c7-493b-9374-b3c461445708">
 
- GPT-4-Turbo, GPT-4, GPT-3.5-Turbo로 실험했다.
