# Points
- LMs (Language Models)가 지니는 context size, out-of-date information 등과 관련된 문제를 해결하기 위해 다양한 augmentation 기법들이 도입됨
- 본인은 그중에서도 RAG (Retrieval Augmented Generation) 관련 내용만을 간단히 정리

# Retrieval-augmented language models (p.11)
- Dense and sparse retrievers
  - Sparse retriever는 document와 query의 sparse한 bag-of-words representation을 사용
  - Dense retriever는 neural network로부터 dense document vector를 획득
  - 결국 문서와 query 간의 관련성을 기반으로 retrieve하는데, 후자가 더 탁월한 성능을 보이는 것으로 알려져 있음
- Conditioning LMs on retrieved documents
  - 최근 QA를 중심으로 하는 knowledge intensive task에 대한 모델 성능 검증이 많이 이뤄지다 보니 크게 주목받고 있음
  - [REALM](https://arxiv.org/abs/2002.08909): end-to-end retrieval system
  - [RAG](https://arxiv.org/abs/2005.11401): retriever를 sequence-to-sequence 모델과 함께 fine-tune
  - [RETRO](https://arxiv.org/abs/2112.04426): large-scale corpus를 사전학습된 frozen BERT embedding과 합쳐 retriever로 사용
  - [Atlas](https://arxiv.org/abs/2208.03299): retriever를 sequence-to-sequence 모델과 함께 학습하여 뛰어난 few-shot learning 능력을 보여주었음 (상대적으로 작은 사이즈임에도)
    <img width="969" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/90cef9b9-bbe6-4a4d-a8e7-5e8982767258">

- Chain-of-thought prompting and retrievers
  - 설명과 예측 결과를 구성하는 reasoning paths를 생성하는 방식
  - 추가적인 학습 또는 fine-tuning이 필요하지 않은 기법
  - [information retrieval chain-of-thought (IRCoT)](https://arxiv.org/abs/2212.10509): CoT를 multi-step QA와 합체
---
링크: https://arxiv.org/abs/2302.07842
