# Apokolips Blog Uploader

A static publishing interface for preparing and publishing image, video and text posts to this repository.

## Pages

- `index.html` — Upload image, video and text posts.
- `posts.html` — Browse all posts uploaded through this repository and view their Like and Comment counts.
- `insights.html` — Analytics dashboard with charts for Likes, Comments, per-post engagement and the last 14 days of activity.
- `analytics.js` — Shared public post reader and read-only connection to the Apokolips community metrics service.

## Publish with GitHub Pages

1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then Save.
4. The uploader will be available at `https://lakindusathsara44-bit.github.io/BlogUploader/`.

## Publishing posts

The uploader writes media into `uploads/` and Markdown posts into `posts/` using the GitHub Contents API. It also updates `posts/index.json` so the Apokolips blog and these dashboard pages can discover each post.

Create a fine-grained personal access token restricted to this repository with **Contents: Read and write** permission. Enter it only into the uploader when publishing. It is held in the current page session and is not stored in localStorage or committed to the repository.

Post structure:
- Media posts: `[Media]`, media reference, then description.
- Text-only posts: `[Text]`, then text content.
- No author attribution is appended.

## Community activity and insights

The Apokolips blog stores shared reactions and comments in the existing Neon database:
- `apokolips_blog_reactions` — reaction type and post slug.
- `apokolips_blog_comments` — comments and replies with post slug.

The Insights and All Posts pages read aggregate activity from those public tables using the same anonymous Neon Auth/Data API configuration as the Apokolips blog. No database password or privileged API key is included in this repository. The dashboard only reads interaction data; Like and Comment actions remain on the Apokolips blog website.

For each uploaded post, the post slug is `uploaded-<filename-without-extension>`, matching the slug used by the Apokolips blog.
