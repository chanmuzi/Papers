AI2

---
# Points
- 요약
  - prompt-win-lose trios로 이뤄진 벤치마크 데이터셋, Reward-Bench를 공개
  - 이를 바탕으로 reward 모델에 대한 평가를 진행한 결과를 제시
  - 리더보드, 평가 코드, 데이터셋 등을 모두 공개 (역시 AI2..)
- 데이터셋 구성
  - 기존의 prompt-completion pairs + 새로 제작한 데이터들
  1. Chat: AlapacaEval, MT Bench 데이터셋에서 선별한 open-ended generation
  2. Chat Hard: MT Bench로부터 비슷한 rating을 갖는 데이터나 adversarial 데이터를 선별
  3. Safety: 민감한 컨텐츠나 부정확한 정보를 제공하는 것에 대해 얼마나 잘 거절하는지를 확인. XSTest, Do-Not-Answer 등의 데이터셋
  4. Reasoning: HumanEvalPack에 나타난 예시를 reformatting하여 사용
  5. Prior Sets: Big-Bench의 subset인 Anthropic HHH, curated subset of Stanford Human Preferences (SHP) 데이터셋 등
- 평가
  - 주된 scoring metric은 accuracy
  - 많은 subset에서 random guessing만도 못한 성능을 보이는 경우가 다수 포착됨
  - per-prompt weighted averaging을 subset 내의 모든 프롬프트에 수행하여 스코어를 normalize
<img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/257af6e3-2691-4289-b15b-fafafa1205c3">

<img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/acd7bc37-ca01-4ba3-90eb-49d3d5a47b6c">


<img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/132c509d-899c-4b5d-9c92-a288395e7013">



---
논문 링크: https://arxiv.org/abs/2403.13787  
리더보드 링크: https://huggingface.co/spaces/allenai/reward-bench
