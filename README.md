# SKKAI 강화학습 스터디

성균관대학교 인공지능 학회 **SKKAI**의 2026-2학기 강화학습 스터디 기록 저장소입니다.

## 스터디 개요

- **일시:** 매주 토요일 16:00–18:00
- **주간 학습량:** 강의 2편 + 논문 1편
- **주요 주제:** RLHF, RLVR, LLM post-training 및 관련 강화학습 기법
- **진행 방식:** 매주 학습 자료와 논문을 나누어 공부하고, 발표와 토론 내용을 기록합니다.

강의 학습은 [RLHF Book의 Extra Resources](https://rlhfbook.com/course#extra-resources)를 중심으로 진행합니다. 해당 페이지에는 강화학습 및 언어 모델 학습을 위한 도서, 강의, 외부 자료가 함께 정리되어 있습니다.

## 참가 인원

| 소속세션 | 이름 | 전공 | 기수 | 직책 |
| :---: | :---: | :---: | :---: | :---: |
| SKKAI ZERO | 정진웅 | 고려대학교 컴퓨터학과 | 2기 | 멘토 |
| X | 김하종 | 성균관대학교 소프트웨어학과 | 1기 | 학회장 |
| Multimodal AI | 김정연 | 성균관대학교 인공지능융합전공(소프트웨어학과) | 2기 | 세션장 |
| Physical AI-Robotics | 조현영 | 성균관대학교 인공지능융합전공 | 2기 | 세션원 |
| On-Device AI Agent | 장우혁 | 성균관대학교 인공지능융합전공 | 3기 | 세션장 |
| AI4Science | 박상혁 | 성균관대학교 신소재공학부(전기전자공학부, 기계공학부) | 4기 | 세션원 |

## 주차별 발표자

강의 제목은 [RLHF Book의 강의 목록](https://rlhfbook.com/course#extra-resources)에 기재된 제목을 사용했습니다. 논문 제목과 발표자는 정해진 뒤 기입합니다.

<table align="center">
  <thead align="center">
    <tr align="center">
      <th align="center">주차</th>
      <th align="center">강의 / 논문</th>
      <th align="center">자료 링크</th>
      <th align="center">발표자</th>
      <th align="center">리뷰 업로드</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="3">1주차<br>(09/26)</td>
      <td align="center"><a href="https://www.youtube.com/watch?v=MMDNaeIFVy8">The ML Foundations of LLM Post-Training</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec0-prereq-review/slides.pdf">PDF</a></td>
      <td align="center"></td>
      <td align="center" rowspan="2"><a href="lecture/week-01/">lecture/week-01/</a></td>
    </tr>
    <tr>
      <td align="center"><a href="https://www.youtube.com/watch?v=o6l6tJQgUg4">Overview</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec1-chap1-3/slides.pdf">PDF</a></td>
      <td align="center"></td>
    </tr>
    <tr>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"><a href="paper/week-01/">paper/week-01/</a></td>
    </tr>
    <tr>
      <td align="center" rowspan="3">2주차<br>(10/03)</td>
      <td align="center"><a href="https://www.youtube.com/watch?v=4gIwiSPmQkU">IFT, Reward Models, &amp; Rejection Sampling</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec2-chap4-5-9/slides.pdf">PDF</a></td>
      <td align="center"></td>
      <td align="center" rowspan="2"><a href="lecture/week-02/">lecture/week-02/</a></td>
    </tr>
    <tr>
      <td align="center"><a href="https://www.youtube.com/watch?v=K_Sj_-1BUMM">RL Motivation &amp; Math</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec3-chap6-p1/slides.pdf">PDF</a></td>
      <td align="center"></td>
    </tr>
    <tr>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"><a href="paper/week-02/">paper/week-02/</a></td>
    </tr>
    <tr>
      <td align="center" rowspan="3">3주차<br>(10/10)</td>
      <td align="center"><a href="https://www.youtube.com/watch?v=i-AIMpZHgeg">RL Implementation &amp; Practice</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec4-chap6-p2/slides.pdf">PDF</a></td>
      <td align="center"></td>
      <td align="center" rowspan="2"><a href="lecture/week-03/">lecture/week-03/</a></td>
    </tr>
    <tr>
      <td align="center"><a href="https://www.youtube.com/watch?v=o4AB5xHIDdM">The Rise of Reasoning Models</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec5-chap7/slides.pdf">PDF</a></td>
      <td align="center"></td>
    </tr>
    <tr>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"><a href="paper/week-03/">paper/week-03/</a></td>
    </tr>
    <tr>
      <td align="center" rowspan="3">4주차<br>(10/17)</td>
      <td align="center"><a href="https://www.youtube.com/watch?v=6g6b4gvO-y0">Direct Preference Optimization</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec6-chap8-dpo/slides.pdf">PDF</a></td>
      <td align="center"></td>
      <td align="center" rowspan="2"><a href="lecture/week-04/">lecture/week-04/</a></td>
    </tr>
    <tr>
      <td align="center"><a href="https://www.youtube.com/watch?v=6nyJ8y8ghsE">Synthetic Data and Modern Post-training Methods</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec7-chap12-synthetic-data/slides.pdf">PDF</a></td>
      <td align="center"></td>
    </tr>
    <tr>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"><a href="paper/week-04/">paper/week-04/</a></td>
    </tr>
    <tr>
      <td align="center" rowspan="3">5주차<br>(10/24)</td>
      <td align="center"><a href="https://www.youtube.com/watch?v=Y2tv5vuaxFs">On &quot;Preferences&quot; and Preference Data</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec8-chap10-11-preferences/slides.pdf">PDF</a></td>
      <td align="center"></td>
      <td align="center" rowspan="2"><a href="lecture/week-05/">lecture/week-05/</a></td>
    </tr>
    <tr>
      <td align="center"><a href="https://www.youtube.com/watch?v=y04JhXpiI4s">Over-Optimization and RLHF's Bad Reputation</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec9-chap14-appb-overoptimization/slides.pdf">PDF</a></td>
      <td align="center"></td>
    </tr>
    <tr>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"><a href="paper/week-05/">paper/week-05/</a></td>
    </tr>
    <tr>
      <td align="center" rowspan="3">6주차<br>(10/31)</td>
      <td align="center"><a href="https://www.youtube.com/watch?v=IwpYxANrpUs">Regularization in RL, Why RL Generalizes, and Why SFT Forgets</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec10-chap15-regularization/slides.pdf">PDF</a></td>
      <td align="center"></td>
      <td align="center" rowspan="2"><a href="lecture/week-06/">lecture/week-06/</a></td>
    </tr>
    <tr>
      <td align="center"><a href="https://www.youtube.com/watch?v=GMry2DzC304">Tool Use, Function Calling and The Road to Agents</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec11-chap13-tools/slides.pdf">PDF</a></td>
      <td align="center"></td>
    </tr>
    <tr>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"><a href="paper/week-06/">paper/week-06/</a></td>
    </tr>
    <tr>
      <td align="center" rowspan="3">7주차<br>(11/07)</td>
      <td align="center"><a href="https://www.youtube.com/watch?v=dFafQmClYq4">The Evolution of Frontier Model Evaluation</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec12-chap16-evals/slides.pdf">PDF</a></td>
      <td align="center"></td>
      <td align="center" rowspan="2"><a href="lecture/week-07/">lecture/week-07/</a></td>
    </tr>
    <tr>
      <td align="center"><a href="https://www.youtube.com/watch?v=xECWRYBxq1E">An Introduction to Character Training</a></td>
      <td align="center"><a href="https://rlhfbook.com/teach/course/lec13-chap17-character/slides.pdf">PDF</a></td>
      <td align="center"></td>
    </tr>
    <tr>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"></td>
      <td align="center"><a href="paper/week-07/">paper/week-07/</a></td>
    </tr>
  </tbody>
</table>

## 저장소 구조

```text
.
├── lecture/
│   └── week-XX/
│       ├── 강의명_발표자이름.md
│       └── 강의명_발표자이름.md
└── paper/
    └── week-XX/
        └── 논문명_발표자이름.md
```

- `lecture/`: 주차별 강의 요약, 발표 자료, 핵심 개념 및 질문
- `paper/`: 주차별 논문 리뷰, 실험 분석, 비판적 의견 및 토론 내용

각 주차는 `week-01`, `week-02`와 같은 형식으로 디렉토리를 만들고, 해당 주차의 강의와 논문 자료를 저장합니다.

## 자료 업로드 방법

발표자는 본인이 맡은 자료를 해당 주차 폴더에 `.md` 파일로 업로드합니다.

1. 강의 자료는 `lecture/week-##/`, 논문 자료는 `paper/week-##/` 폴더에 업로드합니다.
2. 파일명은 아래 형식을 사용합니다.

   ```text
   강의명_이름.md
   논문명_이름.md
   ```

   예시: `RLHF_정진웅.md`, `InstructGPT_김하종.md`

3. GitHub에서는 해당 폴더로 이동한 뒤 `Add file` → `Create new file`을 선택하고, 파일명을 입력해 내용을 작성합니다.
4. 작성이 끝나면 커밋 메시지를 입력해 저장합니다. 로컬에서 작업하는 경우에는 파일을 추가한 뒤 커밋하고 GitHub에 push합니다.

파일에는 제목, 원본 링크, 핵심 내용, 발표에서 다룰 질문을 포함하는 것을 권장합니다. 이미 같은 주차에 다른 사람이 올린 파일은 수정하지 말고, 본인 이름으로 새 파일을 만들어 업로드합니다.

## 기록 가이드

### 강의 기록

가능하면 다음 내용을 포함합니다.

- 강의 제목 및 원본 링크
- 핵심 개념과 수식, 알고리즘
- 강의 내용 요약
- 이해가 어려웠던 부분과 추가 질문
- 발표자 및 발표일

### 논문 리뷰

가능하면 다음 내용을 포함합니다.

- 논문 제목, 저자, 공개 링크
- 문제 정의와 연구 배경
- 제안 방법 및 주요 아이디어
- 실험 설정과 결과
- 한계점 및 비판적 분석
- 스터디 토론 내용과 후속 질문

## 목표

강화학습의 기본기를 바탕으로 RLHF와 RLVR의 핵심 아이디어를 이해하고, 관련 논문을 직접 읽고 설명하며 최신 LLM post-training 연구를 함께 논의하는 것을 목표로 합니다.
