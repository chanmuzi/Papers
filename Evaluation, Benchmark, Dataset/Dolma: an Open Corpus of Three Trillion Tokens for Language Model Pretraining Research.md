# Points
- Abstract
  - 3T 토큰의 영어 corpus. 다양한 source로부터 수집한 데이터셋
  - data curation toolkit을 함께 공개하여 데이터셋 구축 및 활용을 용이하게 함
  - content/quality filter, deduplication, multi-source mixing 등의 기법을 적용
  - 오픈소스 SoTA 모델 OLMo를 학습시킬 때 사용된 데이터셋
  - 허깅페이스 데이터셋 링크: https://huggingface.co/datasets/allenai/dolma
  - 깃허브 toolkit 링크: https://github.com/allenai/dolma
- 데이터셋 source 통계
  - 약 200TB 용량의 raw data를 정제하여 약 11TB 용량의 데이터셋이 됨
  - 토큰 기준으로는 3T 개 수준
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/d4e732ce-2138-4a53-b8e2-136fcc5fe772">

- Dolma
  - 언어 탐지 모델을 사용하여 영어가 아닌 데이터들은 거름
  - 중복 제거의 기준은 document가 아닌 paragraph로 삼음
  - processing pipeline
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/d84d8ae4-c1a8-4231-9d11-48d2ea2074f9">

  - 기타 데이터셋에 대한 파이프라인이 조금씩 다른데 구체적인 내용은 논문에 잘 나와 있음
  - 동일한 문자가 많이 반복되는 것을 탐지하여 제거할 때는 WIMBD라는 tool을 사용
- Training
  - 어떤 processing 기법이 유효한지 아닌지를 판단하기 위해 다양한 실험을 수행
  - Olml-1b 모델을 다양한 벤치마크로 평가
  - 코드 데이터를 사전학습 데이터에 포함시키는 것이 그렇지 않은 것에 비해 전반적인 성능 향상에 도움이 되는 것을 확인
    <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/8e6e7a51-94cb-40a6-9116-0d97371b91d3">

  - 다른 베이스라인 모델들과의 비교
    <img width="600" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/4bbffdb8-9c1c-4a78-8783-d4051b70ac8b">

    - TinyLlama는 학습에 사용된 토큰의 양이 비슷하고, Pythia의 경우 사용된 토큰이 Olmo에 비해 훨씬 적으며, StableLM은 정확한 정보가 알려진 바가 없음
---
링크: https://arxiv.org/abs/2402.00159
