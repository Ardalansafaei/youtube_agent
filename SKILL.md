---
name: youtube-psychology
description: Produces English educational-psychology YouTube packages (viral research, science-backed 6–10 minute narration script, titles, description, hashtags, then numbered cinematic 3D image prompts). Use when the user gives a video topic (Persian or English), asks for a YouTube script, packaging, or writes prompts after reviewing the script.
---

# YouTube psychology channel

Follow this workflow. Read the project subagent prompt if you need the full system text: `.cursor/agents/youtube-psychology.md`.

## When invoked

- The user gives one topic per turn (often Persian). Translate it to English first and continue in English.
- Do not ask questions. If something is missing, guess and put assumptions in one line at the start.
- You cannot watch videos. Analyze titles, descriptions, page text, and transcripts only.
- Write view counts only when seen in a source; otherwise write «تأیید نشده».
- Do not generate images; write prompts only.
- Save files under `output/<topic-slug>/`.

## Phase A (default)

Search the web. Then write:

1. `research.txt` — 5–8 viral/recent videos (prefer last 12 months): title, channel, views if seen, link, one-line why it worked; hook/title/emotion/length patterns; peer-reviewed or official science with study name, year, result. Do not invent sources.
2. `script.txt` — 900–1500 words spoken narration only (no scene directions, emoji, or in-script headings). Strong 15-second hook, clear sections, soft transitions, summary and CTA. Tone: narrative, documentary, warm, slightly promotional, not exaggerated. No definitive medical claims or viewer diagnosis. Cite sources for scientific claims or mark «تأیید نشده».
3. `packaging.txt` — 5 titles (max 60 characters) plus best pick and reason; description with a strong first two lines, summary, scientific sources, searchable phrases; hashtags actually seen on those viral videos (cite source), else «پیشنهادی، تأیید نشده» and 5–8 suggestions.

Stop after Phase A with only this line: «متن را بررسی کن؛ بنویس prompts تا پرامپت‌های تصویر را بسازم.»

## Phase B (only after the user writes `prompts`)

Write `image-prompts.txt` in English, numbered, 10 prompts per script minute (~every 6 seconds), each tied to that section of the script, in order.

File header (once):

Generate ALL images below in one continuous run. Do not ask any questions between images. Every image MUST be based strictly on the attached reference character image. Keep the face, eye color, freckles, hair and body proportions exactly identical in every image. Semi-realistic cinematic 3D style, 16:9.

Start of every prompt:

Same character as the reference image: young woman with brown eyes, light freckles, long wavy dark-brown hair in a half-up style with a small twisted bun at the crown.

Clothing changes with the scene; face and hair never change. Default outfit if unspecified: oversized lavender knit sweater with ribbed cuffs, charcoal wide-leg cropped pants, cream sneakers. Calm psychological mood; no scary, violent, or distressing images.

If long, chunk the file and end each chunk with «ادامه بده»; continue without asking.

After all scene prompts, one cover prompt: 1280×720, 16:9, high quality, consistent character, striking composition with space for text, short title max 5 words.

## Output language

English for script, titles, description, prompts. Keep the Phase A stop line and «تأیید نشده» / «پیشنهادی، تأیید نشده» / «ادامه بده» exactly as specified.
