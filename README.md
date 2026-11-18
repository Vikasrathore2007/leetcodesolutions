# Promptsmith

**Find what your prompt is missing, then rebuild it.**

Promptsmith is a single-page tool for the Prompt Words Hackathon. Paste any prompt and it:

1. Scores it from 0 to 100 against eight essentials of a clear prompt: role, clear task, context, audience, constraints, output format, example, and goal or tone.
2. Explains every missing item with a one-line fix.
3. Rebuilds the prompt into a structured template (`# Role`, `# Task`, `# Context` ...) with bracketed placeholders only for what is missing, ready to copy.

## Why it fits the hackathon

- **Directly about prompts.** The product is prompt quality, so the demo is the pitch.
- **Instant and deterministic.** Rule-based checks, so no API key, no latency, and the same input always gives the same result. Easy to verify.
- **Private.** Everything runs in the browser. No data is sent anywhere.
- **Zero dependencies.** One HTML file with inline CSS and JS. No build step, no images, no GIFs.
- **Accessible.** Labeled inputs, visible keyboard focus, live-updating score, reduced-motion support, responsive layout.

## Try it

Click **Load a weak example** (`Write a blog post about remote work.`). It scores 13/100 and the rebuilt prompt adds role, context, audience, constraints, format, example, and goal sections to fill in.

## Deploy on Vercel

Option A, dashboard: push this folder to GitHub, then **Add New > Project**, import the repo, keep all defaults (Framework: Other, no build command), and click **Deploy**.

Option B, CLI:

```bash
npm i -g vercel
cd promptsmith
vercel --prod
```

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (markup, styles, logic) |
| `vercel.json` | Clean URLs and basic security headers |
| `README.md` | This document |

## How scoring works

Each of the eight checks is worth 12.5 points. A check passes when the prompt matches its pattern (for example, an action verb for Task, or at least 30 words for Context). The rules live in the `CHECKS` array at the top of the script and are easy to extend.

## Possible next steps

Add an optional "improve with an AI model" button, save prompt history, and add more rule packs for coding, writing, and data prompts.
