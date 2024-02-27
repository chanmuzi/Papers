# Points
- Abstract
  - Hint-before-Solving Prompting (HSP)
  - 모델이 문제를 풀기 위해 필요한 knowledge나 key idea에 대한 hint를 먼저 생성하고, 이를 바탕으로 reasoning step를 포함하는 solution을 만들어내도록 하는 프롬프팅 기법을 제시
  - CoT와 결합이 가능한데 이를 오픈소스 모델에 적용했을 때 ChatGPT 이상의 성능을 보여주기도 함
  - GPT-4로부터 얻은 hint를 모아 데이터셋으로 구축. HSPMATH dataset을 Superviesd Fine-Tuning (SFT)에 활용한 실험 결과도 존재
- 다양한 prompting techniques와 비교
  - 기본 (standard), Least-to-Most, tree-of-thought, graph-oc-thought, plan-and-solve prompting
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/b8f21729-68e9-4bac-b118-bd2e824c9e08">

  - HSP 예시 이미지: Hint, Solution 패턴을 few-shot으로 제공
    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/7d32dd3e-e734-4262-ac76-0d52593053d3">

- Experiment
  - Baseline: Standard Prompting (SD), Chain-of-Thought Prompting (CoT), Leaset-to-Most Prompting (LtM), Plan-and-Solve Prompting (PS)
  - Datasets: GSM8K, MultiArith, AQuA, ASDiv, MATH (Mathematical Reasoning) / StrategyQA (SQA), Date Understanding (Date) (Commonsense Reasoning)
- Results
  - HSP를 2-stage로 나누어 적용하는 것이 큰 변화로 이어지지는 않음
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/bc082b5c-8ed3-40d2-add7-510516c8488b">

  - 어려운 태스크에서도 충분히 좋은 결과가 나타날 수 있음. 하지만 모델 by 모델
    <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/f0465d82-d0ee-4093-80cf-3cc966090d5c">

  - 구축한 데이터셋 (HSPMATH)로 SFT를 수행하면 그 결과가 아주 좋음. Llemma-7B 모델에 fine-tuning한 결과는 GPT-3.5와 PaLM-540B의 결과를 상회함
 
    <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/5f94a9d0-6a43-4c1b-86df-5e6b83d32763">

---
링크: https://arxiv.org/abs/2402.14310
