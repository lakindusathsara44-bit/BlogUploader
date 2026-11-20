# Apokolips Blog Uploader

A static publishing interface for preparing and publishing image, video and text posts to this repository.

## Publish with GitHub Pages

1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then Save.
4. The uploader will be available at `https://lakindusathsara44-bit.github.io/BlogUploader/`.

## Publishing posts

The page writes media into `uploads/` and Markdown posts into `posts/` using the GitHub Contents API.

Create a fine-grained personal access token restricted to this repository with **Contents: Read and write** permission. Enter it only into the uploader when publishing. It is held in the current page session and is not stored in localStorage or committed to the repository.

Post structure:
- Media posts: `[Media]`, media reference, then description.
- Text-only posts: `[Text]`, then text content.
- No author attribution is appended.

## Automatic Apokolips blog connection

The Apokolips blog reads Markdown posts from this repository automatically. Each published post receives a stable post slug, which connects it to the existing shared Like/reaction and Comment/reply service on the Apokolips blog. Visitors interact with posts on the website; the uploader itself contains no Like or Comment controls.

Uploaded images and videos are served from this repository's public raw files. The Apokolips blog uses the existing Neon-backed social service for shared reactions and comments.
