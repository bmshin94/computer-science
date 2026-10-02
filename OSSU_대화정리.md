# OSSU Computer Science — 전수조사 분석 & 활용/수익화 전략 대화 정리

> 이 문서는 `bmshin94/computer-science` 레포를 전수조사하고,
> 활용법·기술적 정체·AI 에이전트 적용성·React/PHP 구현·유튜브 제작·수익화까지
> 질의응답한 대화 전체를 정리한 기록입니다.

---

## 📌 문서 정보

| 항목 | 내용 |
|---|---|
| 작성일 | 2026-10-02 |
| 분석 대상 (내 포크) | <https://github.com/bmshin94/computer-science> |
| 원본 레포 (upstream) | <https://github.com/ossu/computer-science> |
| 공식 웹사이트 | <https://cs.ossu.dev> |
| OSSU 커뮤니티 (Discord) | <https://discord.gg/wuytwK5s9h> |
| OSSU 행동 강령 | <https://github.com/ossu/code-of-conduct> |
| 선수 수학 커리큘럼 | <https://ossu.dev/precollege-math> |
| 커리큘럼 기준 문서 (ACM/IEEE CS2013) | <https://www.acm.org/binaries/content/assets/education/cs2013_web_final.pdf> |
| 작업 브랜치 | `claude/peaceful-archimedes-2ff3vq` |
| 관련 문서 | `ANALYSIS_KR.md` (상세 분석 리포트), `CLAUDE.md` (프로젝트 가이드) |

---

## 목차

1. [전수조사 결과 — 이게 뭐 하는 레포인가](#1-전수조사-결과)
2. [쉬운 설명 — 비유로 이해하기](#2-쉬운-설명--비유로-이해하기)
3. [질문 7개 상세 답변](#3-질문-7개-상세-답변)
4. [수익화 아이디어 6가지](#4-수익화-아이디어-6가지)
5. [핵심 요약 & 액션 체크리스트](#5-핵심-요약--액션-체크리스트)

---

## 1. 전수조사 결과

### 1.1 한 줄 정체

**코드가 단 한 줄도 없는 "문서 레포".**
세계 명문대(MIT·하버드·스탠포드·UBC·Northeastern 등) 온라인 강의 **63개를
"올바른 순서"로 배열한 무료 컴퓨터공학 학위 지도**.

`bmshin94/computer-science` = `ossu/computer-science`(Open Source Society University)의 포크.

### 1.2 전수조사 수치

| 항목 | 결과 |
|---|---|
| 전체 파일 수 | 40개 (`.git` 제외) |
| 전체 용량 | 716KB (거의 전부 텍스트) |
| 실행 가능한 코드 | **0줄** |
| 파일 구성 | Markdown 25 + 이미지 7 + Jekyll/HTML 4 + YAML/설정 등 |
| 라이선스 | MIT (© 2015–2023 Open Source Society University) |
| 배포 방식 | `CNAME`(cs.ossu.dev) + Jekyll `minima` 테마 → GitHub Pages |
| 커리큘럼 과목 수 | **63과목** |
| 과목별 Discord 링크 | 36개 |
| 추가 큐레이션 | 강의 60개(`extras/courses.md`) + 도서 63권(`extras/readings.md`) |

### 1.3 폴더 구조 전수조사

```
computer-science/
├── README.md                 ⭐ 29KB — 레포의 본체. 커리큘럼 전체 표
├── ANALYSIS_KR.md               한국어 상세 분석 리포트 (977줄)
├── CLAUDE.md                    프로젝트 가이드 + 페르소나 설정
├── FAQ.md                    ⭐ 9KB — 가장 중요한 "현실 정보"가 숨어있는 파일
├── CONTRIBUTING.md              기여 방법 (RFC 절차 기반)
├── CURRICULAR_GUIDELINES.md  ⭐ ACM/IEEE CS2013 기반이라는 권위의 근거
├── HELP.md                      Discord 안내
├── CHANGELOG.md              ⭐ v8.0.0(2017)이 마지막 정식 버전, "v9 심사 중"
├── CNAME / _config.yml          웹사이트 설정 (cs.ossu.dev)
├── LICENSE                      MIT
│
├── coursepages/              💎 과목별 "실전 공략집" (진짜 보석)
│   ├── intro-cs/                MIT 6.100L — Python 3.8 고정, Spyder 6.0.8 권장,
│   │                            PSET 마감일 매핑, Anaconda 대안 안내
│   ├── intro-programming/       CS50P vs Python for Everybody (둘 중 하나 선택)
│   ├── spd/                     UBC 체계적 프로그램 설계 — DrRacket 설정 스크린샷 2장,
│   │                            깨진 스타터 파일 대체 레포, "지루해도 스킵 금지" FAQ,
│   │                            Space Invaders 프로젝트 지침
│   ├── class-based/             NEU CS2510 — 공식 일정표 재배열, 깨진 강의 영상의
│   │                            유튜브 아카이브 대체 링크, Java 11 필수 경고
│   └── ostep/                💎 6개 파일 506줄 — 운영체제 xv6 커널 실습
│                                (Base 80시간 / Extended 200시간+ 두 갈래 설계)
│
├── extras/
│   ├── courses.md               본 과정 밖 추가 강의 60개
│   ├── readings.md              명저 63권
│   ├── other_curricula.md       경쟁 커리큘럼 비교 + OSSU 차별점
│   └── puzzles-practice-plods.md  "코테 연습 vs 프로젝트" 커뮤니티 논쟁 기록
│
├── .github/
│   ├── ISSUE_TEMPLATE/request-for-comment-template.md   RFC 양식
│   └── workflows/delete-empty-issues.yml  빈 이슈 자동 댓글 + 자동 닫기 봇
│
├── _includes/, _layouts/        Jekyll 템플릿 (파비콘, 푸터, 네비게이션)
└── images/                      로고, 파비콘, DrRacket 설정 스크린샷
```

### 1.4 커리큘럼 구조 (63과목 집계)

| 단계 | 세부 카테고리 | 과목 수 |
|---|---|:---:|
| **Intro CS** | MIT 6.100L (Python) | 1 |
| **Core CS** (필수, ≒ 대학 1~3학년) | Core programming | 5 |
| | Core math (미적분 1A/1B/1C + 이산수학) | 4 |
| | CS Tools (MIT Missing Semester) | 1 |
| | Core systems (Nand2Tetris I·II, OSTEP, Networking) | 4 |
| | Core theory (Stanford 알고리즘 I·II) | 2 |
| | Core security | 5 (4 필수 + 1 선택) |
| | Core applications (DB×3, ML, 그래픽스, SE) | 6 |
| | Core ethics | 3 |
| **Advanced CS** (선택, ≒ 4학년) | programming 6 / systems 3 / theory 3 / infosec 6 / math 5 | 23 |
| **Final Project** | 풀스택, 로보틱스, 빅데이터, 클라우드 등 선택지 | 9 |
| **합계** | | **63** |

- 소요 기간: 주 20시간 × 약 **2년**
- 비용: 학습 자료는 전부 무료 (인증서/채점만 유료 옵션)
- 권위 근거: ACM + IEEE의 **CS2013 표준**에 과목을 매핑

### 1.5 플랫폼 분포 (README 링크 기준)

| 플랫폼 | 링크 수 |
|---|:---:|
| Discord (과목별 채팅) | 36 |
| Coursera | 21 |
| edX | 15 (+ learning.edx.org 3) |
| GitHub | 15 |
| MIT OCW | 9 |
| MIT OpenLearning Library | 5 |
| YouTube | 5 |

### 1.6 ⚠️ 전수조사로 발견한 치명적 이슈

`FAQ.md`에 기재된 내용:

> **2025년 7월, Coursera가 대부분 강의의 무료 청강(audit)을 폐지.
> OSSU는 더 이상 Coursera 강의를 추천하지 않는다.**

그런데 실측 결과:

- README에 **남아있는 Coursera 고유 링크 20개**
  (본 커리큘럼 13개 + Final Project 특화과정 7개)
- 영향받는 주요 과목: `Software Architecture`, `Machine Learning`,
  `Parallel Programming`, 윤리 3과목, 보안 3과목 등
- `CHANGELOG`는 **v8.0.0(2017년)이 마지막 정식 버전**, "v9 심사 중"

**결론: 현재 이 레포는 "완성된 지도"가 아니라 "대규모 공사 중인 지도".**
→ 그 빈틈이 곧 사업 기회다. (4장 참조)

### 1.7 이 레포의 세 가지 용도

| 관점 | 가치 |
|---|---|
| **학습자** | 독학의 진짜 적은 강의 부족이 아니라 "순서"의 부재. 전문가가 짜준 선수과목 그래프를 공짜로 얻는다. 특히 `coursepages/`는 수백 명이 삽질한 결과물. |
| **개발자** | README 표는 사실상 `과목명 \| 기간 \| 주당시간 \| 선수과목 \| 채팅` 스키마의 DB. 파싱하면 진도 추적 앱·로드맵 시각화·추천 엔진 재료. |
| **콘텐츠 제작자** | 전 세계 수만 명이 따르는 커리큘럼인데 **한국어 가이드는 사실상 없음**. 번역·요약·후기 콘텐츠의 블루오션. |

---

## 2. 쉬운 설명 — 비유로 이해하기

### 비유 1: "레시피 책"이 아니라 **"미슐랭 맛집 지도"**

| 흔한 오해 | 실제 |
|---|---|
| "강의가 들어있는 레포" | "강의가 어디 있는지 알려주는 지도" |
| "다운받아서 공부한다" | "읽고 나가서 공부한다" |
| "코드 실습 레포" | "코드 0줄. 전부 글" |

클론해도 영상 한 개, 교재 한 쪽도 없다.
전부 "MIT 가서 이거 듣고, 그다음 Stanford 가서 저거 들어"라고 적힌 **길 안내판**.

### 비유 2: 재료는 넘치는데 **"순서"를 모르는 게 진짜 문제**

| 혼자 독학할 때 | OSSU를 따를 때 |
|---|---|
| "유튜브 강의 100만 개… 뭐부터?" | "1번부터 순서대로" |
| 알고리즘 강의 틀었다가 수학 몰라 좌절 | "이산수학 먼저" 미리 알려줌 |
| 어디까지 했는지 모름 | 체크리스트로 진도 추적 |
| "잘 가고 있나?" 불안 | ACM/IEEE 국제표준 매핑 = 근거 있는 안심 |
| 질문할 사람 없음 | 과목별 Discord 36개 |

→ **OSSU가 파는 건 "강의"가 아니라 "순서 + 확신 + 동료".**

### 비유 3: **"교수님만 없는 명문대 시간표"**

| 일반 대학교 | OSSU |
|---|---|
| 4년 등록금 수천만~1억 | 0원 |
| 교수님 강의 | MIT·하버드·스탠포드 교수 강의(영상) |
| 정해진 학기 | 내 페이스 (2년 권장) |
| **학위증** | **없음 (최대 단점)** |
| 동기·과방 | Discord |
| 학사 조교 | `README.md` + `coursepages/` |

`FAQ.md` 첫 질문이 "OSSU는 학위를 주나요?" → **"아니요."**
즉 **취업 서류용 스펙이 아니라, 실력 그 자체를 만드는 도구**.

### 폴더를 사람 역할로 비유

| 폴더/파일 | 역할 | 쉽게 말하면 |
|---|---|---|
| `README.md` | 4년치 시간표 | 63과목 전체 목록. 이것만 봐도 90% |
| `coursepages/` | 선배의 족보 | "이 영상 깨졌어, 여기 봐", "Python 3.8 써야 해" |
| `extras/` | 도서관 추천 코너 | 추가 강의 60개 + 명저 63권 |
| `FAQ.md` | 학사과 안내 데스크 | "학위 줘요?" "Coursera 유료됐어요" |
| `CURRICULAR_GUIDELINES.md` | 교육부 인증서 | ACM/IEEE 표준 준수 근거 |
| `CHANGELOG.md` | 개정 이력 | v8(2017) 마지막, v9 공사중 |
| `.github/workflows/` | 자동 문지기 | 빈 이슈 올리면 봇이 댓글+자동 닫기 |
| `_includes/`, `CNAME` | 웹사이트 껍데기 | 이 레포가 `cs.ossu.dev`로 자동 변신 |

### 사람들이 놓치는 진짜 알짜: `coursepages/`

예: `coursepages/ostep/`(운영체제)는 6개 파일 506줄.

- **Base 코스(80시간)**: 교재 읽고 숙제 → 커리큘럼 요건 충족
- **Extended 코스(200시간+)**: C + x86 어셈블리를 배우고 **xv6 실제 커널에
  시스템콜 추가**, 로터리 스케줄러 구현

`Project-1B` 문서의 디테일 예시:
- "qemu-system-x86 설치 (배포판에 따라 `qemu`는 틀린 패키지)"
- "Makefile에서 `CPUS := 1`로 설정"
- "수정한 곳에 `// OSTEP project` 주석 → 나중에 디버깅 쉬움"
- "테스트 2는 동시성 강의를 듣고 락을 추가한 뒤에 도전"

→ 수년간 수백 명이 쌓은 노하우. 혼자 하면 이 삽질만 몇 주.

### 현재 상태 요약

```
2017년        : v8.0.0 완성
2025년 7월    : Coursera 무료 청강 폐지
현재          : FAQ "Coursera 추천 안 함" ←→ README에 Coursera 링크 20개 잔존
              = v9 심사 중 (공사 중)
```

즉 **"지도는 훌륭한데, 길 20개가 최근 유료 톨게이트로 바뀌었고 지도는 아직 갱신 중"**.
→ 그대로 따라가면 결제 벽을 만나고, **그 빈틈이 곧 기회**다.

---

## 3. 질문 7개 상세 답변

### Q1. 설치 및 사용법?

**"설치"라는 개념이 없다.** 실행 코드 0줄 → `npm install`도 `pip install`도 불필요.

**방법 A — 그냥 읽기 (0분, 추천)**
<https://cs.ossu.dev> 또는 <https://github.com/ossu/computer-science> 열면 끝.

**방법 B — 포크해서 진도 체크 (OSSU 공식 권장)**

```bash
# 1. GitHub 웹에서 ossu/computer-science → Fork (이미 완료됨)
# 2. 복제
git clone https://github.com/bmshin94/computer-science
cd computer-science

# 3. README.md에서 끝낸 과목 뒤에 체크 표시 추가
#    [Calculus 1A: Differentiation](링크) ✅

# 4. 커밋으로 기록 (GitHub 잔디 = 공부 증명서)
git add README.md
git commit -m "완료: Calculus 1A"
git push
```

공식 README 원문: *"포크해서 완료한 항목에 ✅를 붙이세요. 칸반보드 역할을 하고,
다른 어떤 방법보다 빠릅니다(= 공부할 시간이 남습니다)."*

**방법 C — 내 전용 웹사이트로 띄우기**

```bash
rm CNAME            # 필수! cs.ossu.dev 도메인 충돌 방지
git commit -am "remove CNAME"
git push
# GitHub → Settings → Pages → Source: master
# → https://bmshin94.github.io/computer-science
```

Jekyll `minima` 테마이므로 로컬 미리보기도 가능 (`bundle exec jekyll serve`,
단 `Gemfile`은 직접 추가 필요).

**실전 추천 루틴**

1. `README.md` 전체 1회 통독 → 지형 파악
2. **Intro CS (MIT 6.100L)** 시작 → 어려우면 `coursepages/intro-programming/`의 **CS50P**로 우회
3. **과목 시작 전 반드시 `coursepages/<과목>/README.md` 먼저 읽기**
   (버전 함정, 깨진 링크 정보가 전부 여기 있음)
4. Core CS는 위→아래 순서, **수학은 프로그래밍과 병행** (공식 권장)
5. 과목별 Discord 입장
6. Coursera 과목을 만나면 결제 대신 **Discord / GitHub Issues에서 대체안 탐색**

**비용 정리**

| 항목 | 비용 |
|---|---|
| MIT OCW, OpenLearning Library, 교재, 유튜브 | 완전 무료 |
| edX 청강 | 무료 (일부는 기간 제한) |
| Coursera | **2025년 7월부터 유료** |
| 인증서 | 유료 (전부 선택사항) |

---

### Q2. 이거 플러그인이야? 스킬이야? MCP야?

**셋 다 아니다. 그냥 "문서(Markdown) 레포"다.**

| 구분 | 정체 | 해당 여부 |
|---|---|:---:|
| **플러그인** | 호스트 앱 기능 확장 코드 번들 | ✗ |
| **스킬** | `SKILL.md` + 스크립트로 된 AI 작업 지침서 | ✗ |
| **MCP 서버** | 외부 데이터/툴을 AI에 연결하는 실행 서버(JSON-RPC) | ✗ |
| **문서 레포** | 읽는 Markdown + 정적 사이트 | **✓** |

**`CLAUDE.md` 때문에 생기는 오해**:
그 파일은 **원본 OSSU에 없고 이 포크에만 추가된 것**(프로젝트 가이드 + 페르소나).
`CLAUDE.md`는 "컨텍스트 메모"일 뿐, 플러그인/스킬/MCP가 아니다.

**단, 스킬이나 MCP로 "만들 수는" 있다 (= 기회)**

```
.claude/skills/cs-curriculum-advisor/SKILL.md
---
name: cs-curriculum-advisor
description: CS 독학 로드맵 조언. 사용자가 "뭘 공부해야 해?",
  "이 과목 선수과목이 뭐야?" 라고 물을 때 사용.
---
(README의 63과목 + 선수관계 표를 임베드)
```

MCP 서버로 만들면 진도 DB 연동까지 가능 → 4장 수익화 아이디어 5번으로 연결.

---

### Q3. API 토큰을 사용해야 돼?

**레포를 "쓰는" 데는 전혀 필요 없다 (0개).** 공개 레포 + 읽기 전용.

**뭔가 "만들면" 달라진다:**

| 하려는 일 | 토큰 | 종류 |
|---|:---:|---|
| 레포 읽기/포크/진도 체크 | ✗ | — (git 인증만) |
| GitHub Pages 배포 | ✗ | — |
| 커리큘럼 자동 파싱 앱 (소량) | 권장 | GitHub PAT (비인증 60req/h → 5,000req/h) |
| 깨진 링크 자동 점검 봇 | ✓ | GitHub PAT 또는 Actions 기본 토큰 |
| **AI 학습 코치 제작** | ✓ | **Anthropic API 키 (Claude)** |
| 유저 로그인/진도 저장 서비스 | ✓ | GitHub OAuth App 또는 Supabase 키 |

**보안 수칙**: 토큰은 절대 커밋 금지. `.env` + `.gitignore` 사용.
(이 레포 `.gitignore`에는 이미 `.envrc`, `.direnv/`가 포함되어 있음)

---

### Q4. AI 에이전트를 구축하는 데 도움이 될까?

**세 갈래로 나눠서 판단해야 한다.**

**갈래 A: "에이전트 만드는 법"을 배우는 데 → 간접적**
- LLM, 프롬프트 엔지니어링, RAG, 벡터DB, 함수 호출, 에이전트 오케스트레이션
  → 63과목에 **하나도 없음**
- 이 커리큘럼은 **2013년 ACM 표준 기반** = LLM 시대 이전 설계
- Machine Learning 과목은 있지만 고전 ML(지도/비지도/신경망 기초) 수준

**갈래 B: 에이전트를 "잘" 만드는 기초 체력으로는 → 강력히 도움**

| 에이전트 실무 문제 | 필요한 OSSU 과목 |
|---|---|
| 토큰 비용 폭발, 컨텍스트 최적화 | **알고리즘 I·II** (복잡도, DP) |
| 멀티 에이전트 데드락, 레이스 컨디션 | **OSTEP** (동시성, 락, 스케줄링) |
| 스트리밍 끊김, 타임아웃, 재시도 설계 | **Computer Networking** (TCP, HTTP) |
| RAG 품질, 벡터DB 인덱싱 | **Databases ×3** (인덱스, 트랜잭션, 모델링) |
| 임베딩·유사도·확률 직관 | **Math for CS** + **Linear Algebra** |
| 프롬프트 인젝션 방어 | **Core Security** (위협 모델링, 방어적 프로그래밍) |
| 에이전트 파이프라인 구조 설계 | **Software Architecture**, **OOD** |
| 비결정적 시스템 테스트 | **Software Testing / Debugging** |

**에이전트 개발자 ROI 최상위 4과목**
1. **OSTEP (운영체제)** — 동시성·스케줄링. 멀티 에이전트 설계의 핵심
2. **Algorithms I·II** — 비용/성능 직관
3. **Databases ×3** — RAG의 토대
4. **Computer Networking** — 스트리밍/API 디버깅

**갈래 C: 레포 자체를 에이전트 재료로 → 즉시 가능**

```
"CS 학습 코치 에이전트"
  ├─ 지식: OSSU 63과목 + 선수관계 그래프 + coursepages 노하우
  ├─ 도구: 진도 조회 DB, 링크 생존 확인, 일정 계산
  └─ 역할: "다음에 뭐 들어야 해?" "선수과목 됐어?" "졸업 언제?"
```

**최종 답**: "에이전트 기술 자체"는 ✗ / **"에이전트를 잘 만드는 개발자가 되는 데"는 ✓✓**

---

### Q5. 우리가 React나 PHP로 만들 수 있어?

질문이 두 가지로 읽히므로 둘 다 답한다.

**해석 A: "이 레포를 React/PHP 앱으로 만들 수 있나?" → 매우 쉽다 (주말 프로젝트급)**

README 표가 사실상 DB 스키마이므로 파싱만 하면 된다:

```json
{
  "id": "calculus-1a",
  "title": "Calculus 1A: Differentiation",
  "category": "Core CS / Core math",
  "url": "https://openlearninglibrary.mit.edu/...",
  "altUrl": "https://ocw.mit.edu/...",
  "duration_weeks": 13,
  "effort_hours_per_week": [6, 10],
  "prerequisites": ["high-school-math"],
  "discord": "https://discord.gg/mPCt45F",
  "platform": "MIT OpenLearning",
  "isPaywalled": false
}
```

React 버전 (추천) — "OSSU 한국어 진도 트래커"

```
Next.js 15 + TypeScript + Tailwind + shadcn/ui
├─ 파싱: remark/unified로 README.md → JSON
│         (빌드 타임 또는 GitHub Actions 주간 자동 동기화)
├─ 화면: 로드맵 그래프(React Flow) / 진도 대시보드 / 예상 졸업일 계산기
│         유료화 과목 경보 배지 / 한국어 과목 설명 / 검색·필터
├─ 저장: 1단계 localStorage → 2단계 Supabase(인증 + 진도 동기화)
└─ 배포: Vercel (무료)
```

PHP 버전 (Laravel 11 또는 순수 PHP)

```php
// 가장 간단한 구조
Route::get('/', [CourseController::class, 'index']);
// composer require league/commonmark  ← README 파싱
// MySQL: courses, prerequisites, user_progress 3테이블
// Blade + Alpine.js로 체크박스 토글
```

PHP도 충분히 가능(호스팅 저렴, SSR 간단). 다만 **로드맵 그래프 시각화**는
React 생태계가 압도적으로 편하므로 **Next.js + Supabase** 추천.

**차별화 포인트 (기존 서비스들이 전부 놓친 것)**
> **"2025년 Coursera 유료화 반영 + 무료 대체 강의 추천"** 기능.
> `isPaywalled: true` 과목에 경보 배지 + "대신 이거 들으세요" 추천.
> 이것만으로 원본 README보다 실용적인 제품이 된다.

**해석 B: "이 커리큘럼으로 React/PHP를 배울 수 있나?" → 거의 안 된다**
- React, Vue, PHP, Laravel, Spring, Node 전부 63과목에 **없음**
- 이유: OSSU는 **"특정 언어/프레임워크를 가르치지 않는다"**가 명시적 철학
  (FAQ: "언어별 강의는 Hackr.io나 Reddit을 보세요")
- 그래도 관련 있는 것:
  **Fullstack Open** (Final Project 선택지, React+Node 12주),
  **Software Architecture**, **Databases ×3**, **Web Security Fundamentals**

**현실적 조합**: `OSSU(기초 체력) + 별도 프레임워크 학습(실전 무기)` — 둘 다 필요.

---

### Q6. 유튜브 강의 영상으로 제작 가능할까?

**가능하다. 단, "무엇을" 만드는지가 합법/불법을 가른다.**

**완전히 합법 (해도 되는 것)**

| 콘텐츠 | 근거 |
|---|---|
| OSSU 소개/리뷰/로드맵 해설 | 레포는 **MIT 라이선스** (출처 표기 시 상업적 이용 가능) |
| README 번역·요약·재구성 영상 | MIT 라이선스 |
| "무료 CS 학위 2년 도전" 브이로그 | 내 경험 = 내 저작물 |
| "과목 X 완주 후기 / 난이도 리뷰" | 비평·리뷰 |
| 내가 만든 코드·과제 풀이 설명 | 내 코드 (단 아래 주의) |
| **2025 Coursera 유료화 대체 강의 가이드** | 내 리서치 |
| "Nand2Tetris로 만든 CPU" 제작기 | 내 작업물 |

**하면 안 되는 것 (저작권/규정 위반)**

| 금지 | 이유 |
|---|---|
| **MIT OCW 강의 영상 재업로드** | OCW는 **CC BY-NC-SA** = **비영리(NC)**. 수익화 채널 업로드 시 위반 |
| edX/Coursera 영상 리업로드 | 독점 저작물, 명백한 침해 |
| CS50 영상 수익화 리업로드 | CS50도 **CC BY-NC-SA** (NC) |
| 교재 PDF(OSTEP 등) 통째로 읽어주기 | 저자 저작권 |
| 과제 정답 코드 대량 공개 | 각 강의 **Honor Code 위반** + README Content Policy 경고 |

> **핵심 구분선**: "남의 강의 자료"는 안 되고, "내 설명·내 경험·내 큐레이션"은 된다.
> OSSU 레포 자체(MIT)는 상업적 이용 자유.
> 링크된 **강의 콘텐츠는 대부분 NC(비영리)** — 혼동 금지.

**콘텐츠 시장성 평가**

| 항목 | 평가 |
|---|---|
| 한국어 OSSU 콘텐츠 | 거의 없음 = 블루오션 |
| 검색 수요 ("개발자 독학", "비전공자 CS") | 매우 높음 |
| 신뢰도 | MIT·하버드 브랜드 후광 |
| 제작 난이도 | 낮음 (화면 공유 + 해설) |
| 약점 | 2년 장기물 → 중도 이탈 리스크 |
| 광고 단가(CPM) | 교육/개발 분야 = 높은 편 |

**추천 시리즈 기획안 — 시즌 1 "무료로 컴공 학위 따기" (10편)**

1. "MIT·하버드 컴공 4년 과정, 0원으로 듣는 방법" (후킹)
2. "OSSU 전체 로드맵 10분 정리" — 63과목 지도
3. **"2025년 Coursera 유료화… 그래서 뭐 들어야 해?"** ← 현재 세상에 없는 콘텐츠
4. "비전공자 0일차: Intro CS vs CS50P 뭐부터?"
5. "독학러 90%가 모르는 폴더 `coursepages/` 파헤치기"
6. "수학 어디까지 필요해? 미적분 3개 다 들어야 해?"
7. "Nand2Tetris: NAND 게이트로 테트리스까지 — 컴퓨터 자작기"
8. "운영체제는 OSTEP 하나로 끝 (80시간 vs 200시간 두 갈래)"
9. "OSSU vs 부트캠프 vs 컴공과 — 냉정 비교"
10. "독학 생존 전략: Discord 활용 + 중도포기 방지법"

시즌 2: 완주 챌린지 브이로그 (장기 구독자 + 신뢰 자산)
시즌 3: 프로젝트 제작기 (조회수가 가장 잘 나오는 유형)

**전략**: 1·3번으로 유입 → 브이로그로 구독자 결속 → 유료 상품으로 전환.

---

## 4. 수익화 아이디어 6가지

### 4.0 전제: 왜 "지금"인가

1. **시장 공백** — 한국어 OSSU 가이드가 사실상 없다
2. **긴급한 통증** — 2025년 7월 Coursera 유료화로 전 세계 학습자가
   "그럼 이제 뭘 들어?" 혼란 상태. README는 아직 미반영
3. **수요 확실** — 비전공자 전향, AI 시대 기초 체력 불안, 부트캠프 회의론
4. **원가 0원** — MIT 라이선스 + 제작비 거의 없음
5. **신뢰 공짜** — MIT/하버드/스탠포드 브랜드 후광

---

### 아이디어 1. 유료 코호트 스터디 — 가장 빠른 현금화

개발 0줄, 즉시 시작 가능, 선결제(현금흐름 확보), 후속 상품 검증 데이터까지 획득.

| 항목 | 내용 |
|---|---|
| 상품 | "OSSU Core CS 12주 완주반" (Intro CS → Core programming) |
| 정원 | 10~20명 (카톡/디스코드) |
| 가격 | 월 5~10만원 (또는 12주 패키지 39만원) |
| 운영 | 주 1회 90분 라이브 Q&A + 주간 과제 체크 + 전용 채널 + 이탈 방지 1:1 체크인 |
| 핵심 가치 | 강의가 아니라 **"페이스메이커 + 강제력 + 질문 창구"** (독학 실패 1순위 = 이탈) |
| 월 매출 | 15명 × 7만원 = **약 105만원/월** |
| 리스크 | 낮음 / 단 내 시간 투입이 큼 |

확장: 기수 반복 → 조교 고용 → **"스터디 매니저" 운영 템플릿 자체를 판매**(프랜차이즈화).

---

### 아이디어 2. 한국어 학습 플랫폼 SaaS — 가장 확장성이 큼

```
"OSSU Korea" (가칭)  —  Next.js + Supabase
├─ 무료: 한국어 커리큘럼 뷰어 · 로드맵 그래프 · localStorage 진도
├─ Pro (월 9,900원):
│   ├─ 클라우드 진도 동기화 + 예상 졸업일 자동 계산
│   ├─ 유료화 과목 경보 + 무료 대체 강의 DB   ← 핵심 차별점
│   ├─ 과목별 한국어 핵심 요약 + 함정 노트 (coursepages 번역·보강)
│   ├─ 스터디원 매칭 + 리더보드
│   └─ AI 학습 코치 (아이디어 5와 결합)
└─ Team (월 29,900원): 사내 스터디 관리, 진도 리포트
```

| 항목 | 내용 |
|---|---|
| 개발 기간 | MVP 2~4주 (파싱 자동화로 데이터 입력 비용 0) |
| 수익 모델 | 프리미엄 구독 + 강의 제휴 링크 + 교재 어필리에이트 |
| 손익분기 | 유료 100명 × 9,900원 = **약 99만원/월** |
| 리스크 | 초기 트래픽 확보 → 아이디어 3(유튜브)이 유입 엔진 |
| 성장 전략 | 무료 뷰어로 SEO 장악 → 진도 저장 시 가입 → Pro 전환 |

기술 포인트: GitHub Actions로 주 1회 업스트림 README 파싱 → 변경 자동 반영 +
깨진 링크 탐지. **"항상 최신"이 곧 경쟁력.**

---

### 아이디어 3. 콘텐츠 비즈니스 (유튜브 + 뉴스레터) — 깔때기 최상단

| 수익원 | 규모 추정 |
|---|---|
| 애드센스 | 구독 1만 + 월 조회 20만 → 월 30~80만원 |
| 강의 플랫폼 제휴 (edX 등) | 전환당 수수료 |
| 교재 어필리에이트 (`extras/readings.md` 63권 활용) | 월 10~30만원 |
| 기업 스폰서 (IDE·클라우드·채용) | 편당 50~300만원 |
| **자체 유료 상품 전환 (1·2·4번)** | **실질 수익의 핵심** |

전략: 유튜브 자체 수익은 보너스, **"신뢰 자산 + 트래픽 공장"**이 본질.
3번 영상(Coursera 대체안) → 뉴스레터 구독 → 스터디/SaaS 전환.

준법: OCW/CS50은 **CC BY-NC-SA(비영리)** → 영상 재업로드 금지,
내 해설·화면공유·경험은 허용.

---

### 아이디어 4. 디지털 상품 — 불로소득형

| 상품 | 가격 | 설명 |
|---|---|---|
| "OSSU 한국어 완전 가이드" PDF/노션 | 29,000~49,000원 | 63과목 한국어 설명 + 2025 유료화 대체안 + 주차별 플래너 + 함정 노트 |
| 노션/엑셀 진도 트래커 템플릿 | 9,900~19,000원 | 졸업일 자동 계산, 간트 차트 (공식 구글시트 업그레이드판) |
| "비전공자 CS 독학 생존 매뉴얼" 전자책 | 19,000원 | 이탈 방지, 학습법, 포트폴리오 전환 |
| 과목별 "함정 모음집" | 9,900원/과목 | DrRacket 설정, Java 11, Python 3.8, qemu 설치 등 |

장점: 한 번 만들면 계속 판매 / 재고 0 / 스터디·유튜브와 번들 가능
**주의**: 과제 **정답 코드 판매는 절대 금지** (Honor Code 위반 + 평판 리스크).
"함정·환경설정·학습법"만 판매해야 한다.

---

### 아이디어 5. AI 학습 코치 — 가장 트렌디, 아이디어 2와 시너지

```
"CS 독학 코치 에이전트"
├─ 지식베이스: OSSU 63과목 + 선수관계 그래프 + coursepages 노하우 (RAG)
├─ 도구: 진도 DB 조회 · 링크 생존 확인 · 일정 계산 · 대체 강의 검색
└─ 기능: "다음에 뭐 들어?" / "나 지금 페이스 괜찮아?" / "이 개념 쉽게 설명"
         / "이번 주 계획 짜줘" / 과제 막힐 때 힌트 (정답 아님)
```

| 배포 형태 | 수익 모델 |
|---|---|
| 웹 챗봇 (아이디어 2의 Pro 기능) | 구독 월 9,900원 (추천) |
| Claude **스킬** 패키지 | 유료 배포 또는 리드 유입용 무료 |
| **MCP 서버** 공개 | 오픈소스 → 인지도 → 본 서비스 유입 |

비용 구조: Anthropic API 종량제. **프롬프트 캐싱 + 경량 모델 라우팅**으로
단가를 낮추면 월 9,900원에 마진 확보 가능.
리스크: API 원가 관리, 할루시네이션 → **답변을 레포 원문에 근거(RAG)로 고정**하는 것이 필수.

---

### 아이디어 6. B2B — 단가가 가장 높음

| 상품 | 가격 |
|---|---|
| 기업 신입 개발자 온보딩 커리큘럼 설계 | 건당 300~1,000만원 |
| 사내 CS 스터디 운영 위탁 (분기) | 500~2,000만원 |
| 부트캠프/학원 커리큘럼 라이선싱·컨설팅 | 협의 |

가능한 이유: ACM/IEEE **CS2013 표준 기반**이라는 근거가 있어
**"국제표준 매핑 교육 설계"**로 제안서를 쓸 수 있다.
비전공 출신 주니어의 CS 기초 공백을 메우려는 기업 수요는 확실하다.
B2C(1~5번)로 실적·포트폴리오를 쌓고 진입하는 순서가 안전.

---

### 4.7 종합 평가

| 아이디어 | 시작 속도 | 초기 비용 | 확장성 | 리스크 | 종합 |
|---|:---:|:---:|:---:|:---:|:---:|
| 1. 코호트 스터디 | 매우 빠름 | 0원 | 중 | 낮음 | **1순위** |
| 2. SaaS 플랫폼 | 보통 | 소 | 매우 큼 | 중 | **본진** |
| 3. 유튜브/뉴스레터 | 빠름 | 0원 | 큼 | 낮음 | **유입 엔진** |
| 4. 디지털 상품 | 빠름 | 0원 | 중 | 낮음 | 보조 |
| 5. AI 코치 | 보통 | 소~중 | 큼 | 중 | 2번의 무기 |
| 6. B2B | 느림 | 0원 | 중 | 중 | 후반 고수익 |

### 4.8 실행 로드맵

```
0~1개월  유튜브 3편 업로드 (특히 "Coursera 유료화 대체안")
         + 무료 노션 로드맵 배포 → 뉴스레터 수집
1~2개월  1기 코호트 스터디 모집 (15명 × 7만원) → 첫 현금 확보
         + 수강생 질문 로그 = 상품 기획 데이터
2~4개월  Next.js 무료 뷰어 출시 (SEO 선점) + 유료화 경보 기능
4~6개월  Pro 구독 오픈 + AI 코치 베타
6개월~   디지털 상품 번들 → B2B 제안
```

### 4.9 리스크 체크리스트

| 리스크 | 대응 |
|---|---|
| 강의 콘텐츠 저작권(NC) | 재업로드·번역 전문 배포 금지 / 큐레이션·해설·요약만 |
| Honor Code | 정답 코드 판매·배포 절대 금지 |
| 상표/사칭 | "OSSU 공식" 표현 금지 → "OSSU 기반", "비공식 한국어 가이드" |
| MIT 라이선스 | 파생물에 저작권·라이선스 고지 포함 필수 |
| 원본 레포 변경 | 자동 파싱 + 주간 동기화로 대응 |
| 2년 장기물 이탈 | 12주 단위로 쪼개서 판매 (완주율 상승) |

### 4.10 가장 강력한 단 하나의 무기

> **"2025년 Coursera 유료화로 깨진 OSSU 커리큘럼의 한국어 최신 복구판"**
>
> 원본 README도 아직 못 하고 있고, 전 세계 학습자가 지금 당장 아파하는 문제.
> 이 자산 하나가 유튜브·SaaS·스터디·PDF **전부에 재사용**된다.

---

## 5. 핵심 요약 & 액션 체크리스트

### 5.1 한 장 요약

| 질문 | 답 |
|---|---|
| 이게 뭐야? | 코드 0줄의 **문서 레포**. 명문대 강의 63개를 순서대로 배열한 CS 학위 지도 |
| 언제 써? | CS를 독학할 때 **"무엇을 어떤 순서로"**를 알고 싶을 때 |
| 설치법? | 없음. 읽거나, 포크해서 체크 표시로 진도 관리 |
| 플러그인/스킬/MCP? | **전부 아님** (문서 레포). 단 스킬/MCP로 **만들 수는 있음** |
| API 토큰? | 쓰는 데는 **불필요**. 앱/AI 코치를 만들면 필요 |
| AI 에이전트에 도움? | 에이전트 "기술"은 없음 / 에이전트를 **잘 만드는 기초 체력**엔 강력 |
| React/PHP 가능? | 앱으로 만드는 건 **매우 쉬움** / 이걸로 React·PHP를 배우는 건 **거의 불가** |
| 유튜브 가능? | 해설·리뷰·브이로그는 **합법** / 강의 영상 재업로드는 **불법(NC 라이선스)** |
| 수익화? | 코호트 스터디 → 유튜브 → SaaS → AI 코치 → 디지털 상품 → B2B |
| 가장 큰 기회? | **2025 Coursera 유료화 대응 한국어 최신판** |

### 5.2 지금 당장 할 수 있는 것 (우선순위)

- [ ] `README.md` 통독하고 Intro CS부터 시작 지점 확정
- [ ] 과목 시작 전 `coursepages/<과목>/README.md` 먼저 읽는 습관 만들기
- [ ] 포크에 진도 체크(✅) + 커밋 루틴 세팅
- [ ] (선택) `CNAME` 삭제 후 GitHub Pages로 내 전용 사이트 띄우기
- [ ] README의 **Coursera 20개 링크**를 추려 "유료화 영향 과목 리스트" 만들기 ← 모든 수익화의 핵심 자산
- [ ] 그 리스트 기반으로 **무료 대체 강의 조사 시트** 작성
- [ ] 유튜브 1편 기획: "2025 Coursera 유료화, OSSU는 이제 뭘 들어야 하나"
- [ ] (개발) README → JSON 파서 프로토타입 (remark 또는 commonmark)
- [ ] (개발) Next.js 무료 뷰어 MVP → Vercel 배포

### 5.3 참고 링크 모음

| 구분 | 주소 |
|---|---|
| 내 포크 | <https://github.com/bmshin94/computer-science> |
| 원본 레포 | <https://github.com/ossu/computer-science> |
| 공식 사이트 | <https://cs.ossu.dev> |
| Discord | <https://discord.gg/wuytwK5s9h> |
| 행동 강령 | <https://github.com/ossu/code-of-conduct> |
| 선수 수학 | <https://ossu.dev/precollege-math> |
| 진도 추정 스프레드시트 | <https://docs.google.com/spreadsheets/d/1y2kMsIg9VaHMVmw35x_aH1hpty3V-ZMuV2jA13P_Cgo/copy> |
| ACM/IEEE CS2013 | <https://www.acm.org/binaries/content/assets/education/cs2013_web_final.pdf> |
| CS2023 진행 상황 | <https://csed.acm.org/> |
| LinkedIn (OSSU 등록용) | <https://www.linkedin.com/school/11272443/> |
| 상세 분석 리포트 (이 레포 내) | `ANALYSIS_KR.md` |

---

*이 문서는 Claude Code 세션에서 레포 전수조사 후 작성된 한국어 정리본입니다.*
*OSSU 레포는 MIT 라이선스이며, 링크된 각 강의 콘텐츠의 저작권은 각 기관에 있습니다.*
