---
title: Hit Reaction
date: 2024-03-08
---

Another aspect that enhances immersion in a game is the sense of impact. Aside from visual elements like crisp sound effects or visual effects, what truly makes an impact is the hit reaction. So, how does the hit reaction in this game create such a satisfying sense of impact?

<!--more-->

In Wii Swordplay, when a character gets hit by a sword, the character tilts due to the force of the blow, but a self-balancing mechanism is triggered to regain balance, after which the character returns to the default state, ready to be hit again. Let's take a closer look at how the self-balancing feature works in this game.

When hit, the character's upper body tilts, but the lower body adapts to various factors like the ground's incline, the force of the impact, and the angle of the tilted upper body, resulting in a different leg stance each time. This stance is maintained until the knock-back force caused by the impact reaches zero, after which the character returns to a default stance.

If a pre-defined animation sequence had been used for the hit reaction, the leg stance would look the same every time. However, in this case, the leg positioning changes dynamically. This was implemented using Unity's procedural animation and procedural walking assets. Although the acceleration and deceleration (friction) of the knock-back or the leg positions were not perfectly identical each time, it provided a satisfying sense of impact.
