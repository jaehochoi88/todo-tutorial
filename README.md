# Todo Tutorial

[Claude Code Playbook](https://docs.claude-hunt.com) 강의의 실습용 저장소입니다. Next.js 와 shadcn/ui 로 시작하는 작은 Todo 앱을 단계별로 발전시키며 Claude Code 사용법을 익힙니다.

## 프로젝트 소개

할 일을 추가·수정·삭제·완료 처리하고, 우선순위·마감일·카테고리를 지정해 검색·필터링·정렬할 수 있는 Todo 앱입니다. 데이터는 브라우저 `localStorage`에 저장됩니다. Server Component를 우선으로 하고 클라이언트 상태는 최소한으로 유지하는 구조를 실습합니다.

### 주요 기능

- 할 일 추가 / 수정 / 삭제 / 완료 토글
- 우선순위(높음·보통·낮음) 및 마감일 지정
- 카테고리(업무·개인·쇼핑) 지정 및 카테고리별 필터링
- 키워드 검색
- 전체 / 진행중 / 완료 상태 필터링
- 생성일순 · 이름순 · 마감일순 정렬
- `localStorage` 기반 데이터 보존

## 관련 링크

- 강의 본문: https://docs.claude-hunt.com
- 수강생 결과물 공유: https://claude-hunt.com

## 기술 스택

- Next.js 16 (App Router, Turbopack)
- React 19
- Tailwind CSS v4
- shadcn/ui (radix-mira 스타일, taupe 베이스, phosphor 아이콘)
- TypeScript / ESLint / Prettier
- Vitest / Testing Library (컴포넌트·훅·유틸 테스트)
- 패키지 매니저: bun

## 시작하기

```bash
bun install
bun dev
```

개발 서버는 기본적으로 [http://localhost:3000](http://localhost:3000) 에서 열립니다.

자주 쓰는 스크립트:

```bash
bun dev            # 개발 서버 실행
bun run build      # 프로덕션 빌드
bun run start      # 빌드 결과 실행
bun run lint       # ESLint
bun run typecheck  # tsc --noEmit
bun run format     # Prettier 포맷팅
bun run test       # Vitest 테스트 실행
bun run test:watch # Vitest 테스트(watch 모드)
```

## 챕터별 시작 브랜치

각 레슨은 시작 시점의 코드 상태를 브랜치로 제공할 수 있습니다. 레슨 본문에서 안내하는 브랜치명으로 전환한 뒤 따라가시면 됩니다.

```shell
git checkout <레슨에서 안내하는 브랜치명>
```

## 컴포넌트 추가

shadcn/ui 컴포넌트는 다음과 같이 추가합니다.

```bash
bunx --bun shadcn@latest add button
```

`components/ui` 디렉토리에 컴포넌트가 추가됩니다.

## 컴포넌트 사용

```tsx
import { Button } from "@/components/ui/button";
```

## 프로젝트 구조

```
app/                          # App Router 엔트리 (page.tsx, layout.tsx)
components/                   # Todo 도메인 컴포넌트 (입력, 목록, 검색, 필터, 정렬 등)
components/ui/                # shadcn/ui 컴포넌트
hooks/use-todos.ts            # Todo 상태 관리 및 localStorage 연동 훅
lib/types.ts                  # Todo, Priority, Category 등 도메인 타입/상수
lib/todo-utils.ts             # 검색·필터·정렬 유틸 함수
```

## Contributors

- 토이크레인 - Frontend Developer
