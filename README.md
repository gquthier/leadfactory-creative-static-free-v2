# Lead Factory Creative Static Free Skill V2

Generate a batch of static ad creatives for **Meta Ads and TikTok** using the [HiggsField CLI](https://higgsfield.ai) and GPT Image 2. Works for e-commerce and lead generation. No Photoshop, no Figma — the full creative (visual + embedded text) is rendered by GPT Image 2.

## What's Included

- `SKILL.md` — full instructions: brand brief, variation matrix, 3 prompt rules, 3-step pipeline, prompt structure, visual checklist.
- `scripts/build_plan.py` — edit your brand details and cell list, run it to produce `plan.json`.
- `scripts/gen_run.py` — concurrent batch runner (6 parallel jobs, skip already-done files, job recovery).

## Highlights

- **9 high-CTR native ad formats**: iMessage, Tweet/X review, iOS Note, TikTok Shop review, listicle, stat/data-viz, flat-lay, native FB/IG post, carousel (problem → proof → offer).
- **3 prompt rules** that matter: edge-to-edge layout, ALL CAPS CTA alignment, prompt-only mode for GPT Image 2 (passing `--image` suppresses all text rendering).
- **Testable variation matrix**: each cell isolates one variable (hook, concept format, visual style, proof element, color archetype, format).
- Safe batch runner: skips existing files, recovers lost jobs, never double-bills.

## Quick Start

```bash
# 1. Install HiggsField CLI
brew install higgsfield-ai/tap/higgsfield   # or curl -fsSL https://cli.higgsfield.ai/install.sh | sh
higgsfield auth login

# 2. Edit your brand in build_plan.py, then:
python3 scripts/build_plan.py

# 3. Smoke test (1 image) → review → full batch
python3 scripts/gen_run.py plan_smoke.json
python3 scripts/gen_run.py plan.json
```

## Models

| Model | Credits / image (2k) | Notes |
|-------|---------------------|-------|
| `gpt_image_2` ⭐ | 7 credits | Best text rendering, photorealism — **does not support 4:5, use 3:4** |
| `nano_banana_2` | 2 credits | Best value, supports 4:5 natively |

> CLI calls always consume credits — the free tier is web-app only.

## What Is Excluded

- No internal LeadFactory pipeline or agency tooling.
- No API keys beyond your own HiggsField account.
- No paid scraping, Supabase, CRM, or admin integrations.
- No proprietary script packs or client files.

---

Part of the [Gauthier Thiry LeadFactory Free Skills](https://github.com/gquthier/gauthier-thiry-leadfactory-free-skills) collection.
