# AI with Prayash

> Daily 60-second AI-news Shorts — researched, fact-checked, and scripted by an automated, agentic pipeline.

[![Watch on YouTube](https://img.shields.io/badge/Watch-YouTube-FF0000?logo=youtube&logoColor=white)](https://www.youtube.com/@ai_with_prayash_english)

📺 **Channel:** https://www.youtube.com/@ai_with_prayash_english

---

## What this is

A YouTube Shorts channel covering the fast-moving world of AI — model launches, agent tools, and workflow hacks — in tight, 60-second explainers written for a smart non-technical viewer. Every Short is fact-checked against primary sources, so the hooks stay punchy without overclaiming.

The twist: I don't write them by hand. A pipeline does the research, fact-checking, and scripting, and I review and publish.

## How it's automated

A Python pipeline orchestrates **Claude (Anthropic)** end to end. Each run:

1. **Ingest** — pulls the last 48h from hand-picked YouTube channels (YouTube Data API) and AI newsletters (Gmail).
2. **Cluster** — Claude groups the day's items into the top stories worth covering.
3. **Transcribe** — `yt-dlp` pulls auto-captions from the source videos.
4. **Synthesize (the agentic step)** — Claude writes the script while running **live web searches** to verify every name, number, and pricing claim against primary sources (company blogs, filings, model cards). Hype is stripped, unverifiable claims are dropped, and required caveats are surfaced.
5. **B-roll shot list** — Claude plans the supplemental footage beat by beat, choosing the cheapest credible source per shot (free stock, a real screen-capture, a license-checked clip, or an AI-generated image/video) and writing a ready-to-use prompt or recording recipe for each.
6. **Output** — a per-Short markdown file: title, description, a HeyGen-ready script, fact-check notes, cited sources, and the shot list.

**What makes it agentic:** the fact-checking step isn't a fixed template. Claude decides what to verify, searches the web on its own, and keeps going until it can confirm or drop each claim — the same loop a careful human researcher would run, just automated.

```
ingest ──► cluster ──► transcribe ──► synthesize+factcheck ──► b-roll shot list ──► review & publish
(API/Gmail)  (Claude)     (yt-dlp)      (Claude + web search)        (Claude)            (human)
```

## Stack

- **Python** (standard-library first) orchestrating the **Claude CLI**
- **YouTube Data API** + **Gmail (IMAP)** for sources
- **yt-dlp** for transcripts
- **Claude** with web search/fetch for fact-checking and scripting
- **HeyGen** for the avatar voiceover

## Why

AI news moves faster than anyone can hand-cover it. The bottleneck isn't ideas — it's the grind of verifying claims and writing tight scripts daily. Automating the research and first draft means more Shorts, fewer errors, and a human staying in the loop for judgment and final cut.

---

*This repo is a write-up of how the channel is made. Go watch the result: [@ai_with_prayash_english](https://www.youtube.com/@ai_with_prayash_english).*
