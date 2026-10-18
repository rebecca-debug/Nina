# Brand Wiki — Schema & Operating Rules

Business: Nina Powell. This is a separate wiki from Fantail Weddings — do not merge
or cross-reference the two.

This project maintains a living brand wiki for the business above, following the
pattern in [`docs/brand-wiki-pattern.md`](docs/brand-wiki-pattern.md). You (the LLM)
own the `wiki/` layer entirely. The human owns sourcing, review, and direction.

## Layers

- `raw/` — immutable source material (call transcripts, testimonials, notes, research).
  Never edit files here. Sort new drops into the subfolder that matches what they are:
  `sales-calls/`, `coaching-calls/`, `client-calls/`, `team-meetings/`, `interviews/`,
  `notes/` (brain dumps, one-off context that isn't a call).
- `wiki/` — the brand wiki itself. Markdown articles, organized by category:
  - `identity/` — origin story, founder profile, positioning, values
  - `audience/` — ICP profiles, language patterns, objections, success stories
  - `offers/` — offer architecture, pricing, individual product/package pages
  - `voice/` — voice guide, signature phrases, banned phrases, writing samples
  - `proof/` — testimonials, case studies, metrics
  - `market/` — competitive landscape, trends, content gaps
  - `strategy/` — content strategy, funnel architecture, growth thesis
  - `frameworks/` — proprietary methods and teaching frameworks
  This is a starting scaffold, not a ceiling — create new articles or categories
  when the content calls for it. If something comes up more than twice across
  different sources, it probably deserves its own article.
- `exports/` — condensed, regenerated-on-change summaries derived from the wiki
  (e.g. `brand-context.md`, `voice-guide.md`, `icp-brief.md`). Never edit these by
  hand; regenerate from the wiki.

## First read on every session

Before answering a query, ingesting a source, or changing the wiki, read in order:
1. `wiki/index.md` — catalog of every article with a one-line summary
2. This file — the rulebook
3. `wiki/log.md` — recent activity

Only after that, open the specific articles relevant to the task. Never crawl the
whole wiki — the index and log exist so you don't have to.

## Ingest

When a new source lands in `raw/`:
1. **Classify before extracting.** Don't trust the filename. Read enough of the
   content to classify it: sales call, coaching call, client delivery call, team
   meeting, or interview/content recording. File it into the matching `raw/`
   subfolder if it isn't already there. Each type contributes different
   intelligence — sales calls → objections/buying triggers, coaching calls → ICP
   language + proof points, client calls → delivery patterns, team meetings →
   strategic decisions.
2. Extract: ICP language, voice data, proof points, objections, framework
   explanations, content signals — whatever's actually present.
3. Update every wiki article the source touches. A single call can touch 10+
   articles — that's expected, not a sign of over-filing.
4. **Weight recency.** Where an older and newer source disagree on something
   current (pricing, offers, positioning, ICP, tools), the newer source wins for
   "what the brand is and sells now." Treat sources from the last ~12 months as
   primary; older sources as historical/origin-story context. Flag contradictions
   in `wiki/log.md` and note how they were resolved.
5. Regenerate `wiki/index.md` and append to `wiki/log.md` in the same pass —
   never leave them stale.

If there's no source material yet, interview the human: ask about their business,
clients, story, and methodology, one question at a time, and compile answers
straight into wiki articles.

## Query

Answer from the relevant wiki articles. If the answer is itself worth keeping
(a generated sales page, a competitive analysis, a content comparison), offer to
file it back into the wiki as a new article rather than letting it disappear into
chat history.

## Lint

When asked to health-check the wiki, look for: contradictions between articles,
stale claims superseded by newer sources, orphan articles with no inbound links,
repeated concepts that lack their own page, offers without supporting proof points,
and voice-guide claims that don't match recent call transcripts. Report a health
score and concrete fixes.

## Indexing & logging conventions

- `wiki/index.md`: one line per article — link, one-line summary, category,
  confidence level, source count, last updated. Dense enough to read in one pass.
- `wiki/log.md`: append-only, chronological. Format:
  `## [YYYY-MM-DD] ingest|query|lint | <source or question> | Updated: article-a, article-b`
- Regenerate/append both as part of the same operation that changes the wiki —
  never as separate housekeeping.
