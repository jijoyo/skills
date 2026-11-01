# YouTube Knowledge Factory

Buy on Agensi: https://agensi.io/skills/youtube-knowledge-factory · $9.99

Turn YouTube channels you already follow into a local, searchable knowledge
base — watch zero videos. The radar fetches transcripts only (never the
media), dedupes auto-caption noise into clean Markdown per channel, and
serves your corpus over a local API your agent can grep.

## What it does

1. **Capture** — an idempotent, polite radar (`yt-radar.sh`) walks your
   channel list one video at a time with sleeps between requests.
2. **Convert** — `srt2md.py` turns `.srt` into clean markdown: no block
   numbers, no timestamps, no consecutive duplicates (the classic garbage
   of auto-captions).
3. **Serve** — a zero-dependency Python server exposes the corpus on
   127.0.0.1: a human dashboard plus a JSON search for agents.

## The method (why it works)

- **Per-channel folders**: `knowledge/videos/<channel>/<title>[<id>].md` —
  each file is one transcript, already context-block-sized.
- **Sequential + throttled**: one channel, one video, random 2–5s sleeps,
  15s between channels, a file lock, and a circuit breaker after 3
  consecutive rate-limits. YouTube bans the impatient; it respects the
  polite.
- **Blocklist with cause**: impossible videos (private, members-only,
  age-locked, no captions) are recorded with their reason for 30 days
  instead of retried for eternity.

## Honest limits

Transcripts are auto-captions — punctuation varies. Rate limits are
respected, not fought: a heavy channel takes days. Members-only and private
videos are skipped and logged.

Distilled from a real installation: 6,500+ transcripts across 27 channels.
