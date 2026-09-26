# LLM Post-Training Foundations — Interactive Learning HTML

## 목표

학습자가 일곱 개 핵심 개념을 **백지에서 설명하고 하나의 post-training 흐름으로 연결**할 수 있게 한다. 읽기 완료가 아니라 `이해 → 예측 → 조작 → 재구성`, 그리고 `인식 → 회상 → 설명`을 완료 기준으로 삼는다.

> 최종 질문: “Next-token prediction으로 학습되는 Language Model이 어떻게 SFT를 거쳐 RL 기반 post-training으로 이어지는가?”

이 계획은 요청에 포함된 슬라이드 요약을 근거로 작성했다. 원본 슬라이드 파일은 제공되지 않아 실제 슬라이드와 대조하지 않았다.

## 학습 성과

완료한 학습자는 다음을 설명할 수 있어야 한다.

1. Autoregressive LM의 sequence probability가 조건부 확률의 곱인 이유
2. Hidden state → LM head → logits → Softmax → next-token probability
3. One-hot target의 cross-entropy가 실제 토큰의 NLL이 되는 이유
4. Backpropagation과 learning rate가 parameter update에 미치는 영향
5. Pretraining과 response-only SFT의 데이터 및 loss mask 차이
6. KL의 방향성, 분포 비교, RLHF의 reference policy 제약
7. LM의 state/action/transition/policy/reward 대응 및 RL objective
8. 위 개념을 하나의 pipeline으로 연결하는 설명

## 전체 학습 흐름

```text
Concept Map
  → 1. Autoregressive LM
  → 2. Logits / Softmax
  → 3. Cross-Entropy / NLL
  → 4. Gradient Descent / Backpropagation
  → 5. Pretraining / SFT
  → 6. KL Divergence
  → 7. LM as MDP / RL Objective
  → Integration Lab
  → Adaptive Quiz
  → Misconception Review
  → Blank Page Challenge
  → Feynman Teach-back
  → Final Mastery Test
```

개념 지도에서는 현재 위치와 완료 상태를 보여주고, 각 노드에 마우스를 올리면 한 문장 설명을 제공한다. 각 장의 끝에서는 다음 장과의 인과관계를 한 문장으로 연결한다.

## 장별 공통 루프

| 단계 | 학습자의 행동 | 화면의 역할 |
|---|---|---|
| 1. Intuition | 역할을 일상 언어로 이해 | 작은 예시를 먼저 제시 |
| 2. Visualization | 구조를 흐름으로 파악 | 주요 입력, 변환, 출력을 분리 |
| 3. Formalization | 직관과 수식을 연결 | 정확한 정의와 기호 설명 |
| 4. Experiment | 변수를 직접 조작 | 계산 결과를 즉시 갱신 |
| 5. Predict Before Reveal | 결과를 먼저 예측 | 선택 후 정답과 이유 공개 |
| 6. Mini Quiz | 새 상황에 적용 | 오답 개념 기록 |
| 7. Explain It Yourself | 2~3문장으로 설명 | 작성 뒤 자기 점검 기준 공개 |

## 일곱 개 장의 교육 설계

### 1. Autoregressive Language Model

- **직관:** 이전 토큰을 조건으로 다음 토큰을 하나씩 선택한다.
- **수식:** `Pθ(x₁,…,xₜ) = ∏ₜ Pθ(xₜ | x₁,…,xₜ₋₁)`.
- **실험:** 장난감 next-token 분포에서 토큰을 한 개씩 선택하고, 선택한 조건부 확률을 곱해 문장 확률을 계산한다.
- **핵심 확인:** 한 단계의 확률 변화가 전체 곱에 미치는 영향과 연쇄법칙을 설명한다.

### 2. Logits → Softmax → Probability

- **직관:** LM head가 hidden state를 vocabulary 점수로 바꾸며, logit은 확률이 아니다.
- **수식:** `pᵢ = exp(zᵢ) / Σⱼ exp(zⱼ)`.
- **실험:** 세 토큰의 logit 슬라이더를 움직이고 모든 확률 및 합을 확인한다.
- **핵심 확인:** 한 logit을 올렸을 때 해당 확률, 다른 확률, 전체 합을 예측한다.

### 3. Cross-Entropy / NLL

- **직관:** 정답 토큰에 높은 확률을 주면 손실이 작다.
- **수식:** `H(y,p) = −Σᵢ yᵢ log pᵢ = −log p(true token)` (one-hot target).
- **실험:** 정답 확률 슬라이더와 `−ln p` 곡선의 점을 동기화한다.
- **핵심 확인:** `P(cat)=0.8 → 0.1`일 때 NLL이 증가함을 수치로 설명한다.

### 4. Gradient Descent / Backpropagation

- **직관:** 손실의 변화율을 역전파로 구하고 감소 방향으로 parameter를 이동한다.
- **수식:** `θ ← θ − η∇θL`.
- **실험:** `L(θ)=(θ−2)²`에서 learning rate에 따른 8회 업데이트 궤적을 그린다.
- **핵심 확인:** 작은 값, 적절한 값, 지나치게 큰 값의 수렴·진동을 비교한다. 식의 기호를 클릭해 역할을 확인한다.

### 5. Pretraining → SFT

- **직관:** 두 단계 모두 next-token cross-entropy를 쓸 수 있지만 데이터와 손실을 적용하는 위치가 다르다.
- **수식:** `L_SFT = −Σₜ mₜ log Pθ(yₜ | prompt, y₍<t₎)`.
- **실험:** 일반 텍스트의 전체 토큰 손실 예시와 response-only SFT mask를 토글한다.
- **핵심 확인:** mask가 0인 prompt도 응답 예측의 입력 문맥으로 남는 이유를 설명한다.

### 6. KL Divergence

- **직관:** 현재 policy와 reference policy의 확률 배분 차이를 측정한다.
- **수식:** `D_KL(p∥q) = Σᵢ pᵢ log(pᵢ/qᵢ)`.
- **실험:** 현재 policy의 양의 가중치를 조절해 정규화하고 두 방향 KL을 동시에 계산한다.
- **핵심 확인:** KL의 비대칭성과 reward 추구 중 reference 이탈을 제한하는 역할을 설명한다.

### 7. Language Model as an MDP + RL

| MDP 요소 | 언어모델에서의 대응 |
|---|---|
| State | Prompt + 생성된 토큰 |
| Action | 다음 토큰 선택 |
| Transition | 선택한 토큰을 상태에 추가 |
| Policy | LM의 next-token distribution |
| Reward | 완성된 응답의 RM 또는 verifier 점수 |
| Discount | 단순 예시에서는 1 |

- **수식:** `J(θ)=E_{y∼πθ(·|x)}[R(x,y)]`; KL 제약을 사용할 때는 `−β KL` 항을 함께 고려한다.
- **실험:** `2 + 2 =`에 두 토큰을 선택하고 완성된 응답에 terminal reward를 받는다.
- **핵심 확인:** 토큰별 정답 label이 있는 지도학습과 sparse, delayed sequence reward의 차이를 설명한다.

## 통합과 적응형 복습

- **Integration Lab:** `Transformer → LM Head → Softmax → Cross-Entropy → Gradient Update`를 빈칸에 배치한다.
- **Adaptive Quiz:** 장별 오답 또는 미통과 개념을 우선한다. 각 개념에 대해 장별 미니 퀴즈와 다른 상황의 문항을 제공한다.
- **Misconception Review:** 오답 개념과 설명을 모아 시각화로 돌아가는 바로가기를 제공한다.
- **진행 상태:** `시작 전 / 학습 중 / 퀴즈 통과 / 설명 완료 / 복습 필요`. 브라우저의 localStorage에 저장한다.

## 백지 회상과 설명

### Blank Page Challenge

처음에는 답이나 힌트를 표시하지 않는다. 학습자가 (1) 일곱 개념, (2) 전체 pipeline, (3) 여섯 핵심 수식을 입력한 뒤 기준을 공개한다. 단순 문자열 일치를 정답 판정으로 사용하지 않는다.

### Feynman Teach-back

학습자가 개념을 선택해 초보자에게 설명한다. 저장 후에만 핵심 요소 체크리스트를 보여준다. Cross-Entropy의 예시는 `true-token probability`, `−log`, `확률 증가 → 손실 감소`, `next-token prediction과의 관계`다.

## 최종 평가와 Mastered 기준

1. **Test A — Recognition:** 새 상황의 객관식·예측·오개념 문항 4개를 모두 맞힌다.
2. **Test B — Reconstruction:** 백지 답안에 일곱 개념, pipeline, 여섯 수식, MDP 대응을 적고 제공된 기준으로 직접 대조한다.
3. **Test C — Explanation:** next-token prediction에서 SFT, KL, MDP, RL objective까지 자연어와 수식으로 연결해 설명하고 기준으로 직접 점검한다.

`Mastered`는 일곱 장의 퀴즈 통과와 직접 설명의 체크리스트 자기 점검, Integration Lab 완료, Test A/B/C 완료가 모두 충족될 때 표시한다. Test B에는 MDP 대응을 따로 작성하는 칸도 있다. 자유서술의 의미 정확성을 코드가 자동 채점한다고 주장하지 않는다. 자기 점검의 한계는 UI에도 표시한다.

## UX 및 구현 기준

- 넓은 데스크톱 레이아웃과 모바일 기본 동작
- 개념 지도, 목차, 진행률, 장별 단계 탐색
- 다크/라이트 모드
- 키보드로 조작 가능한 버튼, 입력, 셀렉트와 기본 접근성 레이블
- reduced-motion 설정 존중
- 일곱 실험은 이미지 대신 계산되는 상호작용으로 구현
- 정적 HTML/CSS/JavaScript, 서버나 빌드 단계 없이 실행
- 수식은 외부 렌더러에 의존하지 않는 읽기 쉬운 텍스트 표기로 제공

## 완료 확인

- [x] Markdown 계획 작성
- [x] 7개 장과 공통 학습 루프 구현
- [x] 7개 필수 실험 구현
- [x] Integration Lab, Adaptive Quiz, Misconception Review 구현
- [x] Blank Page, Teach-back, Final Test 구현
- [x] 로컬 진행 상태와 다크 모드 구현
- [x] 실제 브라우저에서 7개 실험의 계산, 마스크 전환, terminal reward 확인
- [x] 첫 화면의 데스크톱 레이아웃과 최종 평가 채점 확인

## 실행

`index.html`을 브라우저에서 열면 된다. 웹 서버가 있다면 이 폴더를 정적 파일로 제공해도 된다. 사용자 답안은 현재 브라우저의 localStorage에만 저장된다.
