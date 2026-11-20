# RipClip

The `ripclip` MCP server connects to the user's RipClip account: it clips long videos (Twitch and Kick streams, VODs, podcasts, video links) into captioned vertical shorts, edits the clips, saves post drafts for TikTok, YouTube Shorts, Instagram Reels and more, and reports how the posts do. The first RipClip call opens a browser to sign in; `/mcp auth ripclip` signs in again.

- Ask whether the user owns the video or has permission before setting `rights` on `import_video`.
- Quote the cost with `estimate_hu` and wait for a clear yes before `find_clips`, `find_moments` or `clip_range`; pass the approved number as `max_hu`.
- RipClip saves drafts only. Never say a post is live or scheduled: say it is a draft and give the `review_url`.
- Edits and new clips are rendered as jobs: poll `job_status`, then show the result with `preview_frame` or `show_clips` and give the `editor_url`.
- YouTube links are not a supported source, and a live stream can be clipped only after it ends.

The skills in this extension (clip-videos, edit-clips, looks-and-templates, post-clips, track-posts) say which tool fits which request. The `/ripclip:` commands run whole journeys, for example `/ripclip:clip-my-stream`.
