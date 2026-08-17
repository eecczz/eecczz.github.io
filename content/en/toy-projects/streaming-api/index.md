---
title: Streaming API
date: 2026-06-13
summary: 'A React and Spring Boot video service that combines delayed previews, direct S3 uploads, asynchronous HLS conversion, and playback APIs.'
highlights:
  - title: Video Preview
    text: Loads a preview only after the pointer remains on a thumbnail, avoiding unnecessary network and decoding work.
    image: detail-hls.jpg
  - title: AWS Media Pipeline
    text: Uses S3, Lambda, and MediaConvert to separate large-file upload and HLS conversion from the application request cycle.
    image: featured.jpg
  - title: Player and Social APIs
    text: Connects the playback URL with video metadata, comments, likes, and subscriptions.
    image: detail-cloud.jpg
links:
  - name: GitHub
    url: https://github.com/eecczz/streamingAPI
featured: true
---

Streaming API is a video service project that connects a React browsing and playback interface to Spring Boot APIs and an AWS media pipeline. Video binaries and HLS outputs are stored in S3, while the relational database keeps post metadata and the `videoUrl` required for playback.

- Tech stack: React, Java, Spring Boot, MariaDB, AWS S3, Lambda, MediaConvert, HLS
- Scope: browse and preview UI, multipart upload orchestration, metadata APIs, asynchronous conversion, playback and social APIs
- Repository: [eecczz/streamingAPI](https://github.com/eecczz/streamingAPI)

## Troubleshooting

### Large video processing occupied the Spring request lifecycle

Direct multipart upload to S3 and event-driven conversion separated binary transfer and transcoding from the application server request.

### Upload requests failed even after the AWS resources were configured

The request path was split into React-to-Spring orchestration and browser-to-S3 upload. Spring CORS was configured for the API calls, runtime files were mapped through `/files/**`, and S3 bucket CORS remained responsible for presigned `PUT` requests and exposing `ETag`.

### Video binaries and post data required different storage responsibilities

Original and converted media stay in object storage. The post table stores title, author, thumbnail, and `videoUrl`, allowing the player to load the media through the URL returned by the read API.

### Loading every thumbnail preview wasted network and decoding resources

The list renders thumbnails first and creates the video element only after a hover dwell time, so passing over a card does not immediately download its preview.

## System Flow

1. React requests multipart upload initialization and signed URLs.
2. The browser uploads each part directly to S3 and completes the upload.
3. An S3 event invokes Lambda, which creates a MediaConvert job.
4. MediaConvert produces the HLS manifest and segments.
5. Spring Boot stores and serves post metadata and the playback URL.
6. The list delays preview loading until hover intent is confirmed.
7. The watch page plays HLS and calls comment, like, and subscription APIs.

## Next Implementation Plan

- Add job-status callbacks with retry and explicit failure states.
- Apply CloudFront signed URLs and cache policies.
- Measure upload and conversion latency, preview request volume, and cloud cost.
