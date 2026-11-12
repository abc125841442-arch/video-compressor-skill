# video-compression

An [Agent Skill](https://skills.sh) that teaches coding agents how to compress video files with `ffmpeg` — picking the right codec, CRF, and preset for web upload, email, mobile playback, or archiving.

```
npx skills add <your-github-user>/video-compression
```

## What it does

When a user says *"compress this video"*, *"my MP4 is too large"*, or *"make this smaller without losing quality"*, the skill walks the agent through:

- Choosing **H.264 / H.265 / AV1** based on the delivery target
- Setting **CRF** (quality vs size) and **preset** (speed vs efficiency)
- Recipes for email size limits, batch folders, screen recordings, and social uploads
- Verifying the output with `ffprobe` before discarding the original

See [`SKILL.md`](./SKILL.md) for the full instructions.

## Quick example

```bash
ffmpeg -i input.mov -c:v libx264 -crf 23 -preset slow -c:a aac -b:a 128k output.mp4
```

Usually cuts size by 50–70% with no visible quality loss.

## Related

Prefer a browser-based tool instead of the command line? [Bay Compress](https://compressvideo.to/) compresses MP4 / MOV / AVI / WebM in the browser — free, no sign-up.

## Install

```bash
npx skills add <your-github-user>/video-compression
```

Works with Claude Code, Codex CLI, Cursor, OpenCode, and [75+ other agents](https://github.com/vercel-labs/skills/blob/main/docs/agents.md).

## License

MIT
