---

title: SpeakUp - AI Agent Communication Coach
date: 2026-06-01
summary: '음성, 시선, 자세, 표정, 침묵, 필러 표현을 실시간으로 분석해 발표·면접 연습을 돕는 AI 에이전트 코칭 서비스입니다.'
highlights:
  - title: 실시간 코칭
    text: 말 속도, 필러, 침묵 등 신호를 분석해 연습 중 바로 피드백을 제공합니다.
    image: featured.png
  - title: 세션 대시보드
    text: 발표·면접·협상 등 상황별 세션을 만들고 연습 흐름을 저장합니다.
    image: https://loremflickr.com/720/450/dashboard,analytics?lock=2401
  - title: AI 리포트
    text: 세션 종료 후 전사와 주요 주의 구간을 바탕으로 개선 리포트를 생성합니다.
    image: https://loremflickr.com/720/450/artificialintelligence,meeting?lock=2402
links:
  - name: GitHub
    url: https://github.com/eecczz/speech-coach
featured: true
---

SpeakUp은 발표, 면접, 협상처럼 말하기 부담이 큰 상황을 AI 에이전트와 함께 반복 연습하는 커뮤니케이션 코칭 서비스입니다. 사용자가 세션명과 집중 포커스를 정하고 카메라 앞에서 말하면, 서비스는 음성·시선·자세·표정·침묵·필러 표현을 분석해 실시간 피드백을 제공합니다.

프로젝트의 핵심은 단순 녹화 분석이 아니라, 연습 중 짧은 코칭을 띄우고 사용자의 질문형 발화에는 에이전트가 대화형으로 답하며, 세션 종료 후에는 전사와 종합 리포트로 다시 복기할 수 있게 만드는 흐름입니다.

- 기술 스택: TypeScript, 웹 프론트엔드, FastAPI 계열 서비스, PostgreSQL
- 구현 포인트: 실시간 코칭 트리거, 세션 저장, AI agent 대화, 리포트 생성 흐름
- 저장소: [eecczz/speech-coach](https://github.com/eecczz/speech-coach)

## 주요 구현 포인트

### 실시간 코칭

![실시간 코칭](featured.png)

말 속도, 필러, 침묵 등 신호를 분석해 연습 중 바로 피드백을 제공합니다.

### 세션 대시보드

![세션 대시보드](https://loremflickr.com/720/450/dashboard,analytics?lock=2401)

발표·면접·협상 등 상황별 세션을 만들고 연습 흐름을 저장합니다.

### AI 리포트

![AI 리포트](https://loremflickr.com/720/450/artificialintelligence,meeting?lock=2402)

세션 종료 후 전사와 주요 주의 구간을 바탕으로 개선 리포트를 생성합니다.
