Apple

---
# Points
- 요약
  - layer마다 다른 수의 파라미터를 사용하는 layer-wise scaling 전략을 사용한 OpenELM family를 공개.
  - publicly available 데이터로만 학습한 모델 중 SoTA를 달성
    
    <img width="700" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/a5157e6f-5315-4ace-9bdd-bd4ef481b831">

- 배경
  - 기존 LLM들은 "isotropic", 즉 같은 configuration을 사용하는 것이 문제점이라고 지적
  - 입력에 가까울수록 smaller latent dimension을 사용하고, 출력에 가까울수록 dimension을 높이는 방식을 도입
- 사전학습
  - decoder-only transformer-based architecture, learnable bias를 사용하지 않음, RoPE, GQA, SwiGLU FFN, flash attention
- Layer-wise scaling
  - attention head의 개수와 FFN multiplier의 개수를 조절하는 방식
    
    <img width="350" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/c183615c-9dc4-46d6-82e8-ee89d91874ed">

  - 위 식에서 $\alpha_{\mathrm{min}}=\alpha_{\mathrm{max}}=1.0$, 그리고 $m_{i}=m$인 경우, standard uniform transformer model과 동일함.
- 학습 데이터
  
  <img width="300" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/4d011ef1-a626-43f9-9ca0-74f6f70ccbaa">

- 평가 결과
  
  <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/36d7e75f-6889-4f67-b57b-822018e6783f">

  <img width="800" alt="image" src="https://github.com/chanmuzi/Papers/assets/101971295/35f6a184-c212-48e0-9dd5-b0902aa84b0e">

---
링크: https://arxiv.org/abs/2404.14619
