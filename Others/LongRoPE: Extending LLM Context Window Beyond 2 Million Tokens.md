Microsoft Research

---
# Points
- Abstract
  - 기존에는 128k tokens가 최대 context window -> 이를 2048k tokens까지 확대
  - 256k training length로 1k step만 fine-tuning한 결과 8x만큼 확대 가능
  - (1) positional interpolation에 있어서 두 가지 형태의 non-uniformities를 이용
  - (2) 256k length로 fine-tuning하는 progressive extension strategy를 도입
  - (3) LongRoPE를 재조정하여 8k 길이의 short context window performance도 유지할 수 있도록 함
- extension method를 활용하는 다른 SoTA 모델들과의 perplexity 비교
  <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/89db4644-8479-4813-8723-73b5735f35ec">

- 기존 다른 방법론들(PI, Dy-NTK, YaRN)과의 비교
  
  <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/4cd2daf6-7a6c-47dc-8074-4fe1db8a406a">

- 학습 알고리즘 및 perplexity 비교 그래프: LongRoPE만 낮은 perplexity를 유지한다는 것을 보여주는 그래프
  <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/68da2de3-fe78-41e6-bd79-4d7b3ea642c9">

- context window를 확장할 때 가장 많이 활용되는 태스크 중 하나인 'Pass key'
  <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c1de9dca-38e0-44a9-a48c-36c696781555">

---
링크: https://arxiv.org/abs/2402.13753
