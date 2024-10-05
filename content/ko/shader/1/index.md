---
title: Wii-Style Shader
date: 2024-03-29
video_url: "https://www.youtube.com/watch?v=Q5CfTyF3sOQ"  # 참고 영상 URL 추가
---

캐릭터와 건물에 적용된 심플하면서도 깔끔한 텍스쳐는 wii게임의 상징입니다. 이러한 텍스쳐가 구체적으로
어떤 특징이 있는지 파악하고, 그것을 unity엔진으로 구현했습니다. 

<!--more-->
wii 텍스쳐 특징
- 단순한 색상 및 쉐이딩
- 광택이 낮은 표면
- 카툰풍의 굵은 외곽선
- 부드러운 애니메이션 텍스처

unity 엔진으로 구현
- Lit 쉐이더를 사용
- Smoothness를 0으로 설정
- 금속성과 광택이 없도록 Metallic을 0으로 설정
- wii 특유의 심플하지만 깔끔한 이펙트는 Emission 속성을 사용하여 재현

이 스타일은 간결하고 깔끔한 외형으로, 하드웨어 성능에 최적화된 단순한 텍스처와 쉐이딩을 사용합니다.
