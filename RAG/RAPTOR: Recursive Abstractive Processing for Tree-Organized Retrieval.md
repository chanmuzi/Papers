[ICLR 2024] Stanford University

# Points
- 요약
  - 텍스트 chunk를 recursively하게 embedding, clustering, summarizing하여 다른 level의 요약을 bottom-up으로 구성하는 트리를 구축하는 방법론
- Related Work
  - Retrieval Methods: TF-IDF, BM25, Fusion-in-Decoder (FiD), RETRO, Atlas, REALM, RAG, Joint Passage Retrieval (JPR), Dense Hierarchical Retrieval (DHR), Hybrid Hierarchical Retrieval (HHR)
  - Recursive summarization as Context
- RAPTOR
  - Tree construction process 이미지
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/cd4f834b-24d4-4554-a0b3-ccb79aa469a9">

  - Clustering Algorithm
    - soft clustering을 사용하며 Gaussian Mixture Models(GMMs)에 근간을 두고 있음
    - cluster의 적절한 숫자를 알아내기 위해 모델 selectino에 Bayesian Information Criterion (BIC)를 사용
    - GMM parameter를 추정하기 위해서는 Expectation-Maximization algorithm을 사용
  - Model-Based Summarization
    - 큰 사이즈의 텍스트 chunck를 간결하고 일관성 있는 summaries로 변경하는 작업
    - gpt-3.5-turbo를 사용
  - Querying: tree traversal vs collapsed tree
    <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/78469f4f-41fa-438b-be05-d9d98dfc1981">

    - 노드를 embedding 할 때는 SBERT를 사용
    - tree traversal: 각 level에서 이전 레이어의 top-k개 노드로부터 새로운 top-k개 노드를 찾는 방식
    - collapsed tree: multi-layered tree를 하나의 layer로 flatten하고, 관련 노드를 한꺼번에 탐색하는 방식
- Experiments
  - Datasets: NarrativeQA, QASPER, QuALITY
  - Metric: BLEU (B-1, B-4), ROUGE (R-L), METEOR (M), Accuracy
  - Baselines: SBERT, BM25, DPR
       
- 소스코드는 [여기](https://github.com/parthsarthi03/raptor)에 공개

---
링크: https://arxiv.org/abs/2401.18059
