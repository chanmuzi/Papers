# Points
- 2021.10 submit
- information retrieval (IR)에서 out-of-distribution (OOD) generalization 능력 평가를 위해 제작된 벤치마크.
  - zero-shot 성능 평가
  - **Be**nchmarking-**IR** **(BEIR)**
  - 18개의 publicly available datasets를 엄선
  - 10개의 retrieval system SoTA로 검정
  - BM25는 성능이 좋은데 cost가 많이 들고, dense/sparse 기반은 성능은 안좋은데 cost가 적게 듦
- BEIR 벤치마크의 다양한 태스크 이미지
  <img width="2117" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/1ef79b03-be89-41b6-8910-e0c267165c59">
 
- BEIR를 구성하는 데이터 통계
  <img width="1648" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/f6ad0a91-1952-40a2-a72e-4e343c75cbdc">

 - 대부분은 binary, 나머지는 3- 또는 5-level로 관련성을 평가한다
- metric
  - Normalised Cumulative Discount Gain (nDCG@k)
  - 모든 데이터셋에 대해 nDCG@10를 사용
- Baselines
  - Lexical Retrieval: BM25
  - Sparse Retrieval: DeepCT, SPARTA, DocT5query
  - Dense Retrieval: DPR, ANCE, TAS-B, GenQ
  - Late-Interaction: ColBERT
  - Re-ranking model: BM-25 + CE
  <img width="1326" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/1b2a6424-7504-4967-8e69-0aee6d9c99c0">

---
논문 링크: https://arxiv.org/abs/2104.08663
깃허브 링크: https://github.com/beir-cellar/beir
