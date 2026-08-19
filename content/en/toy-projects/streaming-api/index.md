---
title: Streaming API
date: 2026-07-12
summary: 'A streaming service connecting a React browsing and playback UI with Spring Boot, AWS S3, Lambda, and MediaConvert.'
links:
  - name: GitHub
    url: https://github.com/eecczz
featured: true
---

<div class="case-study-lead"><p class="case-study-kicker">BACKEND · AI · SYSTEM CASE STUDY</p><p>A streaming service connecting a React browsing and playback UI with Spring Boot, AWS S3, Lambda, and MediaConvert.</p><div class="case-study-meta"><span><b>Role</b> Personal project · upload, media pipeline, post API, playback UI</span><span><b>Validation</b> Large-file upload and HLS playback tests</span></div></div>

## Key Screens
![Content library and video exploration screen](detail-library.png)
![Upload screen for large video files](detail-upload.png)
![Playback screen using a stored video URL](detail-player.png)

## Troubleshooting
### 1. Uploading and converting large videos through the Spring server held requests for too long
The browser uploads raw video to S3, then an S3 trigger invokes Lambda and MediaConvert for transcoding. The application manages metadata and lifecycle states instead of carrying the raw file through the API server.
![Direct-upload and multipart boundary](code-multipart.svg)
### 2. Large browser uploads were blocked even after AWS had been configured
The failure was server-side CORS. `WebConfig` permits the browser origin and maps `/files/**` to the runtime upload directory so post-upload resources are served from the files actually written by the controller.
![CORS and upload-file serving configuration](code-cors.svg)
### 3. A raw video file still needed to appear as a searchable post
The post record stores title, author, description, and `videoUrl` as metadata. The playback screen resolves the media through that URL without storing the video binary in the database.

## Technology Choices
| Technology | Why it was used |
|---|---|
| **React** | For content discovery, upload, and playback interactions. |
| **Spring Boot** | For post metadata, API boundaries, and upload lifecycle handling. |
| **S3 · Lambda · MediaConvert** | To separate large-file transfer and transcoding from the application server. |
| **HLS** | To deliver converted video segments for browser playback. |

## System Flow
![Streaming API system flow](architecture.svg)
1. The client obtains an upload target and sends raw media to S3.
2. S3 triggers Lambda and MediaConvert to create HLS output.
3. Spring Boot persists the post metadata and result URL.
4. The library and player load metadata first, then resolve media at playback.

## Next Implementation Plan
- Add queue-backed conversion status and retry visibility.
- Collect playback, conversion, and storage-cost metrics.
