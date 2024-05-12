NAVER CLOVA, KAIST, LBox, Upstage AI

---
# Points
- 요약
  - text와 layout을 효과적으로 조합하는 방식에 대한 연구
  - BERT Relying On Spatiality, BROS
  - 텍스트의 상대적인 2D 위치 정보를 encode하고 area-masking strategy에 따라 unlabeled document로부터 학습을 진행
  - Key information extraction(KIE)에서의 두 가지 challenge를 다루고 있음
    - 부정확한 text 순서로부터 발생하는 오류를 최소화하기
    - 더 적은 downstream examples로부터 효율적으로 학습하기
- 관련 연구
  - Pre-trained Language Models for 2D Text Blocks
  - Parsers for Document Key Information Extraction
- 아키텍쳐 이미지

  <img width="900" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/2d42819d-fe4b-4c94-b60f-40c452219ed6">

- 텍스트의 위치를 '상대적'으로 반영하는 방식(우)을 '절대적'으로 반영하던 방식(좌)과 비교한 이미지

  <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/7aa6489b-a347-4bb5-948a-c920af950ccf">

- Area-masked Language Model
  - SpanBERT에서 착안한 방식으로, 텍스트 블록을 랜덤하게 고르고 이에 관련된 영역을 마스킹하고 원래 텍스트가 무엇이었는지 주변 컨텍스트를 바탕으로 복원하는 학습법을 제안
  - 이를 token-masked LM(TMLM)과 결합하여 학습한 모델이 BROS

---
링크: https://arxiv.org/abs/2108.04539
