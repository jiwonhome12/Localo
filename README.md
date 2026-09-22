# 로컬로 (Localo)

> 인구감소지역의 축제 · 정부 지원 혜택 · 신청 일정을 한 곳에서 확인하고, AI 코스 추천까지 받는 웹 서비스

**AI 어드벤처 — 지역의 문제를 제품 출시로 해결하는 팀 프로젝트**

---

## 제작 이유

- 인구감소지역에도 좋은 축제·관광 콘텐츠가 많지만, 사람들이 잘 모르고 있음.
- 정부의 여행 지원 제도(지역사랑 휴가지원, 인구감소지역 자유여행상품, 고향사랑기부제 등)는 신청 사이트가 여러 기관에 흩어져 있고, 지역마다 신청 시기도 달라서 일일이 찾아봐야 함.
- **로컬로**는 이 정보를 한곳에 모아 보여주고, 예매처로 바로 연결.

## 주요 기능

| 기능 | 설명 | 담당 |
|---|---|---|
| 지역 · 지원금 조회 | 지역 카드와 필터로 지역을 탐색, 지역 상세에서 축제와 지원금 정보를 확인. 지원금도 계산. | 수민·병지 (FE), 세찬 (BE) |
| 축제 캘린더 · 티켓 연계 | 월별 축제 캘린더, 카테고리 필터·검색, 예매처 바로가기를 제공. | 수민·병지 (FE), 세찬 (BE) |
| AI 코스 추천 | 여행 조건을 입력하면 AI가 여행 코스를 추천. | 수민·병지 (FE), 지원 (BE) |

## 기술 스택

| 구분 | 사용 기술 |
|---|---|
| 프론트엔드 | React, Next.js, Tailwind CSS |
| 백엔드 / DB | Next.js API, Supabase |
| AI | OpenAI API |
| 데이터 | 공공데이터포털 (전국관광지정보 표준데이터 등) |
| 협업 | GitHub, Notion, Figma |
| 배포 | (확정 후 기입) |

## 시작하기

> 프로젝트 초기 세팅이 끝난 뒤부터 사용할 수 있음.

### 미리 설치할 것

- [Node.js](https://nodejs.org) (LTS 버전)
- [Git](https://git-scm.com)
- [VS Code](https://code.visualstudio.com) (추천 에디터)

### 실행 방법

```bash
# 1. 레포 내려받기
git clone https://github.com/<GitHub-계정>/localo.git
cd localo

# 2. 패키지 설치
npm install

# 3. 환경 변수 파일 만들기
cp .env.example .env.local
# 그다음 .env.local 안의 값을 채워요 (Windows는 파일을 복사해서 이름을 바꿔도 돼요)

# 4. 개발 서버 실행
npm run dev
```

브라우저에서 http://localhost:3000 을 열면 화면이 보임.

### 환경 변수

`.env.example`에 어떤 값이 필요한지 적혀 있음. 실제 값은 팀장에게 **비공개 채널(카톡, DM 등)** 로 받기.

| 이름 | 설명 |
|---|---|
| `NEXT_PUBLIC_SUPABASE_URL` | Supabase 프로젝트 주소 |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Supabase 공개 키 |
| `OPENAI_API_KEY` | OpenAI API 키 |
| `PUBLIC_DATA_API_KEY` | 공공데이터포털 인증키 |

> **주의**: `.env.local`은 절대 GitHub에 올리면 안 돼요. (`.gitignore`에 이미 들어 있어요)

## 프로젝트 구조

1주차 아키텍처 설계가 끝나면 여기에 정리해요.

## 팀 소개

| 이름 | 역할 | 담당 | GitHub |
|---|---|---|---|
| 김지원 | 팀장 · BE | 아키텍처 · DB 설계 · 공공데이터 연동 · 코드리뷰 · 주간 QA · 배포 | @ |
| 김수민 | FE | 홈/지역 화면, 축제 캘린더 UI, AI 추천 입력 폼 | @ |
| 강병지 | FE | 지역상세 화면, 필터 UI · 티켓 딥링크, 결과 화면 | @ |
| 박세찬 | BE | 공공데이터 소스 조사, 지원금 계산 로직, 필터 · 검색 API, LLM 프롬프트 | @ |

## 협업 규칙

브랜치 이름, 커밋 메시지, PR 작성법, 주간 QA 방법은 **[CONTRIBUTING.md](./CONTRIBUTING.md)** 를 꼭 읽어주세요.

- 정기 세션: 미정 (초반 30분은 주간 QA)
- `main` 브랜치에는 직접 push 금지. 반드시 Pull Request → 팀장 승인 → 병합
