[Published as a conference paper at ICLR 2024]

# Points
- weight matrix를 보다 작은 (dense) matrix로 대체하는 post-training sparsification, SliceGPT를 제안
  - 파라미터수를 25%까지 줄일 수 있으면서도 Llama-2-70B, OPT-66B, Phi-2에 대해서 각각 99%, 99%, 90%의 zero-shot 성능이 보존됨
  - 덕분에 더 적은 양의 GPU를 사용하면서도 더 빠른 연산이 가능해짐
- 기존 pruning 방식들과의 비교 이미지
  - 다른 방식들과 달리 pruned 행과 열이 정렬되는 방식임
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/8924d077-3eb4-4db4-bec8-aa3e4e6f14ec">

- Method
  - _computational invariance_
  - LayerNorm을 RMSNorm으로 대체
  <img width="350" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/e4edc4af-5d72-4419-8eb0-e9a94d9ab0f0">
 
  - transformation을 block마다 수행
  - PCA를 통해 slicing
- 관련 연구
  - transformer의 구조에 대해 자세히 설명
  - Optimal Brain Surgeon (OBS), Optimal Brain Compression (OBC), GPTQ, SparseGPT
- 실험 결과
  - WikiText-2 데이터셋
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/89a524b4-0f5a-45eb-a5fb-b857a655c8e6">

  - 추론 속도 비교
  <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/33c22b7c-ae1d-4cba-a649-464015469937">

  - 연산 비용 비교
  <img width="500" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/92cf72ff-6069-478a-b3ec-2dd50efb1a0a">

---
링크: https://arxiv.org/abs/2401.15024
