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
- `[Img]`, `[Video]`, or `[Text]`
- Media reference (where applicable)
- Description / post text
- Attribution (defaults to `@GitHub`)

The Apokolips main website must separately read and render Markdown files from this repository for published posts to appear on its blog page. This uploader does not modify the Apokolips repository.
