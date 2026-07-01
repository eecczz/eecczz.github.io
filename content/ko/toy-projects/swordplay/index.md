---
title: Wii Swordplay 클론
date: 2026-06-25
summary: 'Wii Sports Resort 검술대련의 조작감과 타격감을 마우스 기반 PC/WebGL 환경으로 재해석한 Unity 프로젝트입니다.'
links:
  - name: GitHub
    url: https://github.com/eecczz/swordplay
  - name: WebGL
    url: https://eecczz.github.io/swordplay/
featured: true
---

Wii Swordplay 클론은 모션 컨트롤러 대신 마우스 입력으로 검을 휘두르고 공격하는 PC/WebGL 게임입니다. 단순한 공격 버튼보다, 검의 위치와 회전, 타격 타이밍, 피격 반응이 직접적으로 느껴지는 조작감을 만드는 데 초점을 두었습니다.

기존에 정리해 둔 Sword-motion, Hit Reaction, Wii-Style Shader 구현 내용을 하나의 대표 프로젝트로 묶었습니다. 검의 자세를 실제 플레이 영상과 비교하며 조정했고, 절차적 애니메이션과 셰이더를 활용해 원작의 몰입감과 간결한 비주얼을 재현했습니다.

- 기술 스택: Unity, C#, WebGL
- 구현 포인트: 마우스 기반 검 조작, 타격 판정, 피격 반응, Wii풍 셰이더
- 저장소: [eecczz/swordplay](https://github.com/eecczz/swordplay)
