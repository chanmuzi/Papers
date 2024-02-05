# Points
- Abstract
  - 기존 LLM들은 학습 데이터, 아키텍쳐 등등 다양한 요소들을 감춰놓음
  - 하지만 research community가 open LM에 접근할 수 있어야 하는 것이 중요하다고 생각 (Allen Institute for AI)
  - Open Language Model (OLMo)를 공개. 이때 전체 프레임워크, 학습 데이터, 학습 및 평가 코드 등 모델 관련된 다양한 정보를 모두 공개.
- 링크
  - Weights: https://huggingface.co/allenai/OLMo-7B
  - Code: https://github.com/allenai/OLMo
  - Data: https://huggingface.co/datasets/allenai/dolma
  - Evaluation: https://github.com/allenai/OLMo-Eval
  - Adaptation: https://github.com/allenai/open-instruct
- OLMo 모델의 주요 특징
  - 모델 사이즈 및 토큰 관련 정보
    <img width="500" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/9dfb2adf-79e7-4a27-9a0e-f288d86ee5e3">

  - No biases, Non-parametric layer norm, SwiGLU, Rotary positional embeddings (RoPE), Vocabulary
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/98678deb-4b65-49e1-aaaa-ba35398aa07a">

  - 사전학습 데이터로 Dolma를 사용 (AI2에서 이전에 공개한 사전학습용 데이터셋)
    - language filtering, quality filtering, content filterintg, deduplication, multi-source mixing, tokenization
  - 데이터 분석을 위해서 WIMBD tool을 사용 (이것 역시 본인들이 이전에 공개한 것)
- Evaluation
  - offline 평가를 위해 Catwalk 프레임워크를 사용
  - downstream tasks에 대해 zero-shot 퍼포먼스를 기록
  - held-out data에 대한 퍼포먼스를 확인하기 위해 perplexity를 측정하는 벤치마크 Paloma를 사용
- Training
  - ZeRO optimizer, FSDP
  - AdamW optimizer, clip gradients
  - Dloma에 포함된 2T개의 token
  - AMD 기반의 LUMI vs NVIDIA 기반의 MosaicML → 거의 동일한 결과
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/d2f7e49f-1d6d-4c45-9ea1-3f3d33c4df18">

- Results
  - baselines:  LLaMA-7B, LLaMA2-7B, MPT-7B, Pythia-6.9B, Falcon07B, RPJ-INCITE-7B
  - benchmarks: arc, boolq, openbookqa, sciq, hellaswag, piqa, copa, winogrande
    <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/2ac2a797-f188-4f25-b123-9c6b258db797">

  - power consupmtion and carbon footprint
    <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/6757d682-0d25-4190-a4fb-5c0d90696afb">

- Artifacts Released (현재까지 공개한 것): 상업적으로도 이용 가능한 Apache 2.0 License로 공개
  - training & modeling code
  - training model weights: 7B model, 7B-twin-2T, 1B model
  - training data Dolma
  - Dolma's toolkit to construct new datasets, WIMBD for dataset analysis
  - evaluation codle using Catwalk for downstream task evaluation, Paloma for perplexity-based evaluation
- 앞으로 공개할 것
  - Training logs, ablations, and findings
  - Weights & Biases logs for training runs
  - Adapted OLMo with instruction-tuning and RLHF, including its training and evaluation code and data using Open Instruct library
  - 65B 모델은 현재 학습 중
 
---
링크: https://arxiv.org/abs/2402.00838
