University of Washington, Google Research, Harvard University

---
# Points
- Matryoshka Representation Learning (MRL)
  - 다른 차원의 embedding을 하나의 임베딩으로 여러 downstream tasks에 대해 adpative하게 학습
  - 이미지 분류, vision + language, BERT를 대상으로 방법론의 타당성을 검증
  - 차원을 줄이더라도 다른 차원 축소 기법 대비 정확도가 잘 유지된다는 것이 contribution
    <img width="650" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c8a6e708-cb91-4b18-a166-633a4294511b">

  - 위 이미지에서 볼 수 있는 것처럼 기존 2048 차원의 벡터를 16차원까지 줄이는 것도 큰 문제가 없음. 만약 이를 encoder 기반의 언어 모델에도 동일하게 적용할 수 있다고 한다면 retrieval의 bottleneck을 줄이는 데 기여할 수 있지 않을까라는 생각이 듦.
    
- 아키텍쳐 이미지
  
  <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/e7888df0-2fee-422b-880b-5dddd521a32b">



---
링크: https://arxiv.org/abs/2205.13147
