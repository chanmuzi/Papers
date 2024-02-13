# Points
- Abstract
  - context understanding 벤치마크를 제안
  - 4개의 task와 9개의 데이터셋으로 구성
  - quantized(3-bit post-training quantization) models의 in-context-learning 능력을 dense 모델의 능력과 비교
- 4개 task & 9개 데이터셋 이미지
  <img width="850" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/e0670c0f-2203-4b05-826e-9f688c16a9ff">

- 관련 연구
  - In-context Learning (ICL) Evaluation: MMLU, SUPER-GLUE
  - Model Compression for LLMs: compression during training / compression associated with fine-tuning / post-training methods
---
## Tasks & Datasets
1. Coreference Resolution (CR)
   - 텍스트 내의 전반적인 이해가 일관성 있는지를 검증
   - WSC273, OntoNotes 5.0 데이터셋을 활용
   - multiple-choice task로 전환
   - 5개의 요소로 구성
     
     <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/ef446018-b51e-48dc-a0f1-fb8cbd5ee60d">

   - MUC, $B^{3}$, $CEAF_{\phi4}$로부터 획득한 CoNLL F1 score를 메트릭으로 사용
2. Dialogue State Tracking (DST)
    - 대화 내 key information을 tracking하는 태스크
    - MultiWOZ 데이터셋을 활용
    - joint goal accuracy (JGA)를 메트릭으로 사용
      
      <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/0de04d24-fa7d-4275-8513-c09cf6b38685">
      
3. Implicit Discourse Relation Classification
     - 두 개의 segments(arguments)의 관계를 판별하는 태스크 (네 개 중 하나를 고르는 분류 문제)
     - PDTB-3 corpus를 사용
     - 각 segment를 elementary discourse units (EDUs)라고 부름
       <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/7c8e882b-7ca8-4130-9d31-db3f2f097288">

     - accuracy를 메트릭으로 사용

4. Query Rewriting
     - 대화에 포함된 마지막 발화를 대회와 독립적인 context-free 문장으로 변환하는 태스크
     - 다섯 개의 데이터셋: MuDoCo with QR annotations, QReCC, InCar, GECOR, CANARD
     - BLEU & ROUGE를 메트릭으로 사용
       
       <img width="400" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/1a0626af-ed2a-43c2-9554-85de6992ad76">

---
- Experiments & Results
  - OPT (from 125M to 2.7B) / LLaMA (from 7B to 65B) / GPT-3.5-turbo
  - zero/one/5/8/10-shot
    <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/531441c8-c450-4969-8bc3-7b27ba5a6e59">

  - In-Context Learning을 활용하더라도 Fine-Tuned 모델에 한참 미치지 못하는 퍼포먼스가 확인됨
  - 일반적으로 알려져 있는 것과 달리 OPT-2.7B이 LLaMA-7B을 넘어서는 결과를 보여줌
  - LLaMA-7B 모델과 30B 모델을 quantize한 것을 비교하면 둘 다 요구하는 메모리 크기는 비슷하나 후자가 뛰어난 성능을 보여줌
    
    <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/4257e80d-3fcc-42f6-ac11-0958d0e87d7e">

---
링크: https://arxiv.org/abs/2402.00858
