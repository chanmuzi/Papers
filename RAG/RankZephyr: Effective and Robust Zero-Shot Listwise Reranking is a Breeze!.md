# Points
- open-source 모델과 proprietary 모델 간의 reranking 능력 gap을 줄이고자 한 연구
- NovelEval 테스트 셋에 대해서는 GPT4보다도 뛰어난 성능을 보일 정도의 성과
- Zephyr 7B 모델을 사용하여 RankZephyr 모델을 학습
- 적절한 prompt를 사용하는 것이 중요. 본 연구에서도 꽤나 체계적인 프롬프트를 디자인했음
  <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/784a03e3-8fbb-4c2a-9dae-38ca55801761">

- background에 BERT 기반의 reranking 모델들의 등장 배경과 piarwise, listwise 패러다임의 등장이 잘 설명되어 있음
  - 결국 reranking은 top k/top n개를 **'추천'** 하는 방식이기 때문에 정통 추천 알고리즘이나 관련 모델들에 대한 이해가 필요함
- top 20개 후보를 뽑는 과정을 100K개 training queries로 실험
  - GPT3.5, GPT4로부터의 distillation을 비교
  - 8 x RTX A6000로 40시간 학습했다고 함
  <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/b9d2bab2-b131-447b-9947-95c5f4c488d2">

---
링크: https://arxiv.org/abs/2312.02724
