---
title: Smart CCTV Fall Detection
date: 2026-08-13
summary: 'An Edge-AI monitoring project that reduces nursing-home RTSP false positives through three-stage pose, fall-object, and site-context zero-shot validation.'
links:
  - name: GitHub
    url: https://github.com/eecczz
featured: true
---
<div class="case-study-lead"><p class="case-study-kicker">BACKEND · AI · SYSTEM CASE STUDY</p><p>An Edge-AI monitoring project that reduces nursing-home RTSP false positives through three-stage pose, fall-object, and site-context zero-shot validation.</p><div class="case-study-meta"><span><b>Role</b> Edge-AI field internship · data, models, post-processing, field validation</span><span><b>Validation</b> Live nursing-home RTSP environment</span></div></div>

## Key Screens
![Fall event in the live monitoring environment](detail-event.png)
![Hard validation accuracy for fall and normal-person scenes](detail-accuracy.png)
![Hard validation confusion matrix](detail-validation.png)

## Troubleshooting
### 1. Pose estimation alone was unstable for occlusion, distance, and vertical falls
Joint confidence, body angle, aspect ratio, and dwell-time heuristics changed with camera angle and occlusion. Pose remained the first candidate stage, while a `fall/person` detector became the second verifier.
### 2. The detector still confused sitting, bending, and lower-body occlusion with falls
Hard negatives for sitting, bending, and partial occlusion were added. Overlapping or adjacent boxes were grouped, and a fall survived only when confidence and body coverage were sufficient.
### 3. Model output alone could not interpret the site context
The final verifier compares candidate visual features with site-specific prompts such as a person fully lying on the floor, sitting on a chair, bending, or partially hidden by furniture.

## System Flow
![Smart CCTV Fall Detection system flow](architecture.svg)
1. Pose keypoints and body tilt produce a fall candidate from RTSP frames.
2. A YOLO `fall/person` model verifies the cropped candidate.
3. Nearby boxes are grouped and confidence and coverage are measured.
4. Visual features and site-specific prompts perform zero-shot validation.
5. Only events above 0.70 confidence and the time condition are confirmed and sent to snapshots, DB, and alerts.
