# Points
- re-ranking 벤치마크 (for IR)
  - TREC, BEIR, Mr.TyDi
  - metric: nDCG@10
  <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/92c11e17-94e1-4259-91f7-024c7276ab38">

- re-ranking 자체가 LLM의 기존 objective와 다르다는 점을 지적 (NovelEval 구축)
- ChatGPT의 ranking 능력을 어떻게 작은 모델에 distill 할 것인가 (permutation distillation 도입)

- Passage Re-Ranking with LLMs
  - 최근에는 LLM의 zero-shot 능력을 활용하기도 함
  - log probability에 기반하고 있기 때문에 ChatGPT, GPT-4와 같이 뛰어난 ranking model을 활용하지 못함
- Method
  - Instructional Permutation Generation: query와 passage간의 relevance를 바탕으로 내림차순 정렬
  - Sliding Window Strategy: window size, stpe size를 정해 입력 토큰의 한계를 극복
  - API를 다 쓰면 너무 비싸므로 이를 distillation
    - 모델이 생성한 permutation을 타겟으로 설정. specialized model $s_{i} = f_{\theta}(q,p_{i})$가 distillation 대상
    - MS MARCO로부터 10K queries를 추출하고 BM25를 사용하여 각 20개의 후보 passages를 탐색
- 평가
  - BM25를 사용하여 top-100 passages를 retrieve
  - nDCG@{1,5,10}
  - window size는 20, step size는 10
  - TREC and BEIR 벤치마크에 대한 nDCG@10 결과
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/082f9eb7-6dea-4ba3-aff1-c8de1e9cd214">

  - Mr.TyDi에 벤치마크에 대한 nDCG@10 결과
  <img width="350" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/8dbbebfa-95a2-489f-8ae6-27a1b5d8c736">

---
링크: https://arxiv.org/abs/2304.09542
