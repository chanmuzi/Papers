AI21labs

---
# Points
- Abstract
  - Transformer-Mamba mixture-of-experts (MoE) 아키텍쳐를 지닌 Jamba를 제시
  - Transformer와 Mamba layer가 일정 비율로 번갈아가며 등장하며, 이중 일부에 MoE를 추가
  - 높은 throughput과 small memory 사용량이 특징
  - 256K context window
- 아키텍쳐 이미지
  <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/714be18d-9c1b-4396-beac-6c9666a8443d">

- notation (default 값)
  - $l$: layer의 개수, 4
  - $a:m$: attention:mamba layer의 비율, 1:7
  - $e$: single MLP 대신 MoE가 등장하는 주기, 2
  - $n$: layer마다 포함된 expert의 숫자, 16
  - $K$: 각 토큰에 사용되는 top expert의 숫자, 2
    
    <img width="450" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/9ccee587-ef27-4140-a183-d373986f9a77">

- 기타 테크닉
  - RMSNorm을 적용하여 loss spike를 방지
  - Grouped-Query Attention (GQA)
  - SwiGLU
  - BPE
  - 64K vocab size
- 평가
  - needle in a haystack: long context를 지원하는지 확인하는 태스크
    <img width="500" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/bcd64924-0ef8-4427-a629-1de093b5fcf2">

  - 기타 Academic Benchmarks 등등: Common sense reasoning, Reading Comprehension 등
---
링크: https://arxiv.org/abs/2403.19887
