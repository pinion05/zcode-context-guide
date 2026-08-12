# ZCode 컨텍스트 매니지먼트 — 전문가를 위한 첫 안내서

ZCode(@zcode/desktop, GLM-5.2 기반 데스크톱 코딩 에이전트)의 **컨텍스트 매니지먼트 기법**을
역엔지니어링(bundle ↔ 런타임 교차검증)으로 복원해 시각화한 단일 페이지 가이드.

에이전트 루프와 컨텍스트 방법론에 해박하지만 ZCode는 처음인 독자를 대상으로,
**“익숙한 패턴(prompt caching · sliding window · /compact · tool truncation 등) → ZCode의 실현과 Δ”** 로 전개합니다.

## 다루는 내용
- ZCode 프로세스 아키텍처와 커널의 위치
- 7-소스 컨텍스트 예산(`rS` enum)
- 다블록 캐시 시스템 프롬프트 계층
- 컨텍스트 윈도잉(messageOffset/Count)
- Compaction 엔진(1급 턴, 5 트리거, `compaction.terminal`)
- Target-Budget 연속(continuation) — ZCode만의 차별적 설계
- 툴 출력 예산화(budgetStrategy: artifact/truncate)
- 입력 큐 모델(3-way delivery), 재시도·백오프, 영속 스키마

## 보기
- GitHub Pages: https://pinion05.github.io/zcode-context-guide/
- 로컬: `index.html`을 브라우저로 열면 됩니다 (외부 폰트 CDN만 참조).

## 출처
`@zcode/desktop v3.7.5`의 `out/host`·`out/scheduler` bundle(esbuild, keep-names)과
런타임 `db.sqlite`·`tasks-index.sqlite`·`model-io` rollout을 교차검증해 복원.
