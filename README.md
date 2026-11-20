# RipClip for Gemini CLI

RipClip turns long videos (Twitch and Kick streams, VODs, podcasts, video links) into captioned vertical clips, edits them, saves post drafts for TikTok, YouTube Shorts, Instagram Reels, Facebook, Threads and Bluesky, and tracks how the posts do. This extension connects Gemini CLI to a RipClip account so all of that works from the terminal.

## Install

```
gemini extensions install https://github.com/RipClipDev/ripclip-gemini
```

Then ask Gemini to use RipClip, for example "turn my latest Twitch stream into short clips". The first call opens a browser to sign in to RipClip and approve its permissions and a monthly Horizon Unit limit (`/mcp auth ripclip` does it again).

## What is inside

- `gemini-extension.json`: one remote MCP server, `https://ripclip.org/mcp/` (streamable HTTP, OAuth sign-in).
- `GEMINI.md`: the rules Gemini follows with RipClip (permission for videos, cost approval, drafts only).
- `skills/`: clip videos, edit clips, looks and templates, post clips, track posts.
- `commands/ripclip/`: typed shortcuts such as `/ripclip:clip-my-stream`, `/ripclip:edit-my-clip`, `/ripclip:plan-my-week` and `/ripclip:how-are-my-posts-doing`.

## Data handling

The extension talks to one place: RipClip's server at `https://ripclip.org/mcp/`, over a sign-in you approve (OAuth). It contains no programs and no other network destinations. RipClip saves drafts only and never publishes a post by itself. Work that uses Horizon Units is quoted first and runs only after you approve it.

- Documentation: https://ripclip.org/ai-assistants
- Privacy: https://ripclip.org/privacy
- Terms: https://ripclip.org/terms
- Support: https://ripclip.org/support (support@ripclip.org)

MIT licensed (LICENSE). The RipClip name and logo are trademarks of RipClip and are not covered by that licence.
