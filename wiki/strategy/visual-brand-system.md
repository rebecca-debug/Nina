# Visual Brand System — AI Generation Pipeline

A ready-to-use prompt pack (`raw/research/ai-brand-system-prompt-pack-2026-10-18.md`) for generating Nina Powell's visual identity through an image-generation AI, built from the same market intelligence behind [identity/brand-core.md](../identity/brand-core.md) and [offers/the-sovereign-somaticist.md](../offers/the-sovereign-somaticist.md). The pipeline itself (5 prompts, run in order) is unchanged from the 2026-10-16 version — only the brand payload fed into it changed (new name, slogan, method, tone). An earlier copy of the pack exists at `raw/research/ai-brand-system-prompt-pack-2026-10-16.md` under the superseded "Unhinged Reclamation" name — use the 10-18 version.

**Confidence:** Medium for the process (it's a concrete, reusable pipeline); low for any visual output, since nothing has been generated yet.

## Pipeline (5 prompts, run in order)
1. **Style Extraction** — feed 1-3 design references (Pinterest, websites, ads) to extract a visual brand board: palette, typography, image/composition logic, signature device, grid system.
2. **Brand Adaptation** — reuses that board's exact layout/system, swaps in Nina's wording (brand name, slogan, hooks, section labels) without changing the visual world.
3. **Logo / Wordmark** — 4 wordmark options, 4 marks/monograms, 2 lockups, black/white/accent versions, one recommended direction.
4. **Brand Design System** — turns the chosen logo + campaign board into a reusable system: social templates, carousel covers, ad creative, website hero direction, do/don't examples.
5. **Website Hero** — a conversion-focused 16:9 hero section (headline, subhead, CTAs, trust strip) ready to hand to a developer.

## Explicit guardrails baked into the prompts
Avoid: full redesign/new art direction when adapting, generic AI slop, stock-template branding, text-heavy strategy documents, overcrowded layouts, vague or guru-sounding copy.

## Status
Not yet run. The full prompt text lives in the raw source — pull from there verbatim when ready to execute rather than retyping from this summary.

---
**Sources:** `raw/research/ai-brand-system-prompt-pack-2026-10-16.md` (2026-10-16)
**Last updated:** 2026-10-18
