# KMU-Moodiary-Client

> AI 감정 일기 Moodiary 웹, 감정 달력 (Next.js)

Moodiary는 하루 한 편 일기를 쓰면 AI가 감정을 분류하고 친구처럼 답장을 달아 주는 일기 서비스다. 국민대학교 재학 중이던 2024년 10월에 만들었고, 이 저장소는 그 웹 프런트엔드다.

## 주요 기능
- 카카오 로그인
- 월별 달력에 날짜마다 감정 색(HAPPY, SAD, ANGRY, SURPRISED, NEUTRAL) 표시
- 오늘 일기를 아직 쓰지 않았으면 작성 버튼 표시
- 일기 보기 화면에서 본문과 AI 피드백 확인, 수정·삭제

## 기술 스택
| 영역 | 기술 |
|---|---|
| 언어 | TypeScript |
| 프레임워크 | Next.js 14 (App Router), React 18, Zustand, Tailwind CSS 3, react-toastify |
| 인프라 | Docker (standalone 출력) |

## 구조
```
src/app/
  page.tsx                   감정 달력
  login/                     카카오 로그인
  oauth/kakao/callback/      로그인 콜백
  write/[id]/                일기 작성·수정
  view/[id]/                 일기와 AI 피드백 보기
src/store/useUserStore.ts    유저 상태
src/util/axiosInstance.ts    /api 호출
```

## 실행
```bash
pnpm install
pnpm dev
```
`/api` 요청은 `next.config.mjs`의 rewrite로 배포된 서버에 전달된다.

## 관련 저장소
- [KMU-Moodiary-Server](https://github.com/son-daehyeon/KMU-Moodiary-Server) — API 서버

---
2024 · 개인 프로젝트 · 보관됨
