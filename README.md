# Clipdock cloud deployment branch

This isolated branch deploys the Clipdock personal video-downloader to Render.

- No changes are made to the repository's default branch.
- The complete source is distributed as a gzipped tar archive in `clipdock-source.tar.gz.b64` to preserve the original multi-file frontend from the ZIP supplied in ChatGPT.
- The Dockerfile extracts that archive during the build and installs yt-dlp and FFmpeg.
- Configure `CLIPDOCK_CLOUD=1`, `CLIPDOCK_USERNAME=clipdock`, and a randomly generated `CLIPDOCK_PASSWORD` with at least 20 characters as Render environment variables.
- Only download videos you are authorised to save. Render free instances are not guaranteed always-on, can lose temporary files, and use metered outbound bandwidth.
