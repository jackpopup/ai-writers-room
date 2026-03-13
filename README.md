<p align="center">
  <img src="https://img.shields.io/badge/Claude_Code-Skill-blueviolet?style=for-the-badge&logo=anthropic" alt="Claude Code Skill" />
  <img src="https://img.shields.io/badge/Agents-7_Specialists-orange?style=for-the-badge" alt="7 Agents" />
  <img src="https://img.shields.io/badge/Drafts-3_Versions-green?style=for-the-badge" alt="3 Drafts" />
  <img src="https://img.shields.io/badge/Languages-EN_KO_JP-blue?style=for-the-badge" alt="Multilingual" />
</p>

<h1 align="center">AI Writers Room</h1>

<p align="center">
  <strong>7명의 AI 전문가가 협업하는 글쓰기 스킬 for Claude Code</strong><br/>
  기자 · 편집자 · 카피라이터 · PD · 팩트체커 · 교열 · 헤드라인 디렉터
</p>

<p align="center">
  <a href="#-설치">설치</a> ·
  <a href="#-작동-방식">작동 방식</a> ·
  <a href="#-벤치마크">벤치마크</a> ·
  <a href="#-콘텐츠-템플릿">템플릿</a> ·
  <a href="#-quick-mode">Quick Mode</a>
</p>

---

## What is this?

**AI Writers Room**은 Claude Code용 스킬(Skill)입니다. 설치하면 글을 쓸 때 7명의 전문가 AI가 병렬로 협업하는 뉴스룸 시스템이 자동으로 작동합니다.

```
"바이브코딩이 소프트웨어 산업을 어떻게 바꾸고 있는지 블로그 써줘"
```

이 한 줄로:
- 4명이 기획 회의 → 방향 합의
- 3가지 톤으로 동시 집필 (위트 / 서사 / 팩트)
- 팩트체커 + 교열 + 편집자 3인 검수
- 헤드라인 디렉터가 제목 9개 제안
- 비교표와 함께 최종 추천

**단순히 "글 잘 쓰는 AI"가 아니라, "글 잘 만드는 시스템"입니다.**

---

## 🚀 설치

### Option 1: .skill 파일 (가장 간단)

[Releases](../../releases) 에서 `ai-writers-room.skill` 다운로드 후:

```bash
claude install-skill ai-writers-room.skill
```

### Option 2: 이 레포에서 직접

```bash
git clone https://github.com/jackpopup/ai-writers-room.git
claude install-skill ai-writers-room/ai-writers-room.skill
```

### Option 3: SKILL.md 직접 복사

`SKILL.md` 파일을 Claude Code 프로젝트의 스킬 디렉토리에 복사해도 동작합니다.

---

## 🔄 작동 방식

```
┌─────────────────────────────────────────────────────────┐
│                    AI Writers Room                        │
│                                                          │
│  Phase 1: PLAN          4명 병렬 기획                     │
│  ┌──────┐ ┌──────┐ ┌──────┐ ┌──────┐                    │
│  │ 기자 │ │카피  │ │  PD  │ │편집자│  → 방향 합의서       │
│  └──────┘ └──────┘ └──────┘ └──────┘                    │
│                      ↓                                   │
│  Phase 2: DESIGN     구조 설계 → 구성안                   │
│                      ↓                                   │
│  Phase 3: GATE    ✋ 사용자 승인                          │
│                      ↓                                   │
│  Phase 4: DO         3명 병렬 집필                        │
│  ┌────────┐ ┌────────┐ ┌────────┐                       │
│  │  A안   │ │  B안   │ │  C안   │                       │
│  │ 위트풀 │ │ 서사적 │ │ 팩트형 │  → 3개 초안            │
│  └────────┘ └────────┘ └────────┘                       │
│                      ↓                                   │
│  Phase 5: CHECK      3명 병렬 검수                        │
│  ┌──────┐ ┌──────┐ ┌──────┐                             │
│  │팩트  │ │교열  │ │편집  │  → 검수 리포트               │
│  │체커  │ │팀장  │ │  자  │                              │
│  └──────┘ └──────┘ └──────┘                             │
│                      ↓                                   │
│  Phase 6: POLISH     헤드라인 디렉터                      │
│  ┌──────────────────────┐                               │
│  │ 제목 9개 + 리드문 3개 │  → 제목/요약                   │
│  └──────────────────────┘                               │
│                      ↓                                   │
│  Phase 7: ACT        비교표 + 최종 추천                   │
│  ┌──────────────────────┐                               │
│  │  ✅ 사용자 최종 선택  │  → 완성 원고                   │
│  └──────────────────────┘                               │
└─────────────────────────────────────────────────────────┘
```

---

## 📊 벤치마크

동일한 글쓰기 요청에 대해 **스킬 사용 vs 미사용** 비교 테스트 결과:

| 지표 | AI Writers Room | 스킬 없음 | 차이 |
|------|:---:|:---:|:---:|
| **다중 초안** | ✅ 3가지 버전 | ❌ 1개만 | +200% |
| **팩트 체크** | ✅ 출처 검증 + 미검증 플래그 | ❌ 없음 | — |
| **헤드라인 옵션** | ✅ 9개 + 리드문 | ❌ 1개 | +800% |
| **분량 정확도** | ✅ 목표 ±10% | ❌ 2.5배 초과 | — |
| **Assertion Pass Rate** | **100%** (12/12) | 33% (4/12) | **+67%** |
| 토큰 사용량 | ~44K | ~24K | 1.8x |
| 소요 시간 | ~6분 | ~1분 | 6x |

> 💡 스킬 없이도 Claude는 글을 잘 씁니다. 이 스킬의 가치는 **글의 품질**이 아니라 **제작 프로세스**에 있습니다 — 다중 시각, 전문 검수, 선택지 제공.

---

## 📝 콘텐츠 템플릿

글 유형을 말하면 자동으로 최적 설정이 적용됩니다:

| 유형 | 톤 | 분량 | 추천 모드 |
|------|-----|------|-----------|
| **블로그** | 대화체, 접근성 | 1,200-2,000 words | Full Pipeline |
| **칼럼/사설** | 권위적, 논증적 | 800-1,500 words | Full Pipeline |
| **뉴스레터** | 친밀한, 1인칭 | 500-1,000 words | Full or Quick |
| **장문 피처** | 몰입적, 문학적 | 2,000-5,000 words | Full Pipeline |
| **보도자료** | 전문적, 팩트 중심 | 400-600 words | Quick Mode |
| **소셜 스레드** | 펀치, 스크롤 스톱 | 5-15 posts | Quick Mode |

---

## ⚡ Quick Mode

풀 파이프라인이 필요 없을 때:

```
"빨리 써줘" / "just write it" / "skip the process"
```

Quick Mode는 서브에이전트 없이 1개 초안을 바로 작성하되, 스킬의 구조적 감각(템플릿, 편집 관점, 헤드라인 옵션)은 그대로 적용합니다.

---

## 👥 The Team

| 역할 | 전문 분야 | 활약 단계 |
|------|----------|----------|
| 🗞️ **시니어 기자** | 팩트 기반 집필, 논점 구성 | Plan, Do(C안) |
| ✂️ **편집자** | 구조, 흐름, 가독성 | Plan, Check |
| ✍️ **카피라이터** | 후킹, 임팩트, 톤앤매너 | Plan, Do(A안) |
| 🎬 **PD/프로듀서** | 스토리텔링, 감정선 | Plan, Do(B안) |
| 🔍 **팩트 체커** | 출처 검증, 논리적 비약 탐지 | Check |
| 📝 **교열팀장** | 문법, 맞춤법, 문체 일관성 | Check |
| 🎯 **헤드라인 디렉터** | 제목, 리드문, 리듬감 | Polish |
| 🎨 **풍자 일러스트레이터** | 시각적 은유, AI 이미지 프롬프트 | On Request |

---

## 🌏 다국어 지원

- 한국어, 영어로 트리거 가능
- 선택적 번역 단계 (Localize): EN, JP 병렬 번역 지원
- 문화적 맥락 치환 포함 (예: 카카오톡 → LINE for JP)

---

## 🔧 요구사항

- **Claude Code** (Claude Code CLI 또는 VS Code Extension)
- **Claude Opus 4** 이상 권장 (서브에이전트 병렬 실행 지원)
- 별도 플러그인/라이브러리 **불필요** (독립 스킬)

---

## 📄 License

MIT License — 자유롭게 사용, 수정, 배포하세요.

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/jackpopup">POPUP STUDIO AI</a>
</p>
