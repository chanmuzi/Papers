# Points

- 2023 EMNLP

## 배경
- 텍스트 요약과 같은 분야에서 LLM을 직접 학습시키거나 deploy하는 것은 너무 많은 비용을 초래
- 데이터의 양도 많이 필요함
- 이를 해결하기 위해 _knowledge distillation_ (KD)과 같은 기법이 등장
- ChatGPT를 distill하고 smaller LM을 fine-tuning하는 방법을 제시

## Approach
![image](https://github.com/chanmuzi/Papers/assets/101971295/45a21efe-9149-4014-a633-ef0679c1ad15)

- USE-Cosine과 Shannon Score를 평가 지표로 사용

과정은 크게 세 가지 단계로 이루어져 있음.
1. Data Selection
- 데이터셋 D로부터 synthetic summaries를 생성하기 위한 N개의 대화를 선택
- 각 validation 대화에 대해서 top k개를 추출하는데, 이때 k는 약 N/M 정도의 값임


2. Prompt Retrieval
- 유사도 기반의 prompt retrieval을 수행
- validation 데이터셋에서 가장 유사한 대화를 USE-consine을 기준으로 ㅂsampling
- 추출된 문서들은 ChatGPT를 통해 요약됨


3. Data Filtering
- 위에서 확보한 데이터의 품질을 보장하기 위해 teacher 모델이 데이터를 filtering 함
- 전체 과정을 시각화 한 것은 다음과 같음
  ![image](https://github.com/chanmuzi/Papers/assets/101971295/59ae837c-06e5-4dfc-b3d2-d529b2a09e22)


## 실험
- StackExchange의 대화 데이터를 사용
  - 예산 이슈로 인해 100K로 제한
  - Ubuntu & NYC forum & BC3 email 요약 corpora 사용
    ![image](https://github.com/chanmuzi/Papers/assets/101971295/b2cf1f64-4332-4ff9-9a00-eb39fa5ad36d)

    ![image](https://github.com/chanmuzi/Papers/assets/101971295/2ba050b5-d8cd-4005-ba12-9aa3402f578e)

- ChatGPT를 teacher model로 사용
- BART 모델을 student로 사용

---
링크: https://aclanthology.org/2023.emnlp-main.753/
