---
title: SpeakUp - AI Agent Communication Coach
date: 2026-06-01
summary: '음성, 시선, 자세, 표정, 침묵, 필러 표현을 실시간으로 분석해 발표·면접 연습을 돕는 AI 에이전트 코칭 서비스입니다.'
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
