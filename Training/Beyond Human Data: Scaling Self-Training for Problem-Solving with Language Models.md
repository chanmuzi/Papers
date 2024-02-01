[Google DeepMind]

# Points
- REST $^{EM}$
  - 사람이 직접 annotate 해야 하는 데이터를 활용하는 fine-tuning은 효율적이지 않음
  - scalar(binary) feedback을 활용할 수 있는 수학 문제나 코딩에 활용할 수 있는 기법: MATH reasoning, APPS coding benchmarks
  - (1) 모델로부터 sample을 생성하고 binary feedback을 사용하여 필터링
    - Generate(E-step)
    - likelihood of obtaining high rewards
  - (2) 모델을 필터링된 sample에 대해 fine-tune
    - Improve(M-step)
    - reward-weighted negative log-likelihood loss
  - (3) 위 과정 반복
    <img width="980" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/b8949f06-52e0-4b05-a325-a28a8a696d11">

  - PaLM-2 models로 실험
- Keywords and Related Work
  - RL from external feedback, EM for RL, Language, LLMs, Reasoning, Coding, Self-Improvement
  - Expert Iteration: ExiT
  - Self-Taught Reasoner: STaR
  - Rejection Sampling Fine-tuning: RFT
  - Iterative Maximum Likelihood: IML
  - Reward weighted regression: RWR
  - Reward ranked fine-tuning: RAFT
- Experiments
  - Evaluation: GSM8K, Hungarian HS finals, HumanEval, Big-Bench Hard
  - MATH, APPS 둘 다에 대해 성능 향상이 확실하게 확인됨. 하지만 iterations를 무작정 늘리는 것은 좋지 않을 것
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/1a24b548-1a34-4768-b228-b192398dca88">

    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/8cced984-4311-43a2-9dc4-7d68d289b8f5">

  - 과적합이 발생하는데, 특히 데이터의 숫자가 더 적은 APPS에 대해 더 잘 일어남
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/f338060e-8976-4d02-ab89-bb51b6b71e57">

---
링크: https://arxiv.org/abs/2312.06585
