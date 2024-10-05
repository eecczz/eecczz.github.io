---
title: Sword-motion
date: 2024-03-29
video_url: "https://www.youtube.com/watch?v=Q5CfTyF3sOQ"
---

One of the biggest contributors to the fun of Wii swordplay is the interactive motion of the sword. When users hold the Wii remote as if swinging a sword, the in-game character moves in a way that closely mimics the player's actual stance, greatly enhancing immersion.
<!--more-->
This interactive sword movement is far from simple. The motion includes rotation, and rotation occurs around an axis. Let's consider how to set the rotation axis based on how we actually hold a sword.

When we hold a sword and take different stances, the position of the sword is determined by three rotational axes: the shoulder, elbow, and wrist joints. Since the game needs to respond to all possible real-world stances, it also requires three axes of rotation. However, if multiple axes are involved in rotation simultaneously, it becomes extremely complex to calculate appropriate weighting for each axis or account for changes in lower axes' positions due to rotation along higher axes. Therefore, the sword's position was designed to shift dynamically based on a single rotation axis.

After watching countless gameplay videos, predicting the code for sword movement, and tweaking numbers and formulas, I successfully implemented sword motion that closely mirrors the actual game. As expected, the interactive sword motion added a significant level of immersion and enjoyment to the gameplay.
