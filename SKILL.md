---
name: feedback-radar
description: Analyze public community feedback about a video game from Reddit, YouTube, X/Twitter, Facebook, Instagram, forums and the web, and produce a source-backed report with direct links. Supports nine analysis types - negative sentiment (the default), update/patch feedback, bugs and technical issues, missing features and QoL, monetization, player spending impact, balance and competitive issues, event feedback, and custom questions. Use when the user asks what players think or complain about, wants a community sentiment or backlash report, asks how players reacted to a patch or event, or asks whether complaints affect spending. Triggers on phrases like "analyze [game]", "what are players unhappy about", "community feedback on", "player sentiment", "backlash", "reaction to the update".
argument-hint: "[game name] [analysis type]"
author: Umang Srivastava
version: 1
---

# Feedback Radar

Analyze public community feedback about a video game, find the strongest problems and trends, and deliver a source-backed report. Every material finding must trace back to a real, dated, linked source.

The skill exists to answer: *"What is the gaming community saying, what are the strongest problems or trends, what evidence supports those findings, and what should the product or business team understand from them?"* The exact question changes with the selected analysis type.

## Core principles

- **Negative Sentiment Analysis is the default.** Spending Impact is optional, never automatic.
- **Evidence-led and auditable.** Findings are source-backed, dated, deduplicated and linked.
- **Current-year focused.** Primary evidence is limited to the analysis period below.
- **Non-assumptive.** Do not assume every analysis is about spending. Do not assume sentiment caused business outcomes.
- **Honest about access.** Never pretend to have read something you could not open, and never fabricate content.
- **Evidence and interpretation stay separate.**

## References

Load each file only when you reach the step that needs it.

| File | Load when | What it covers |
|---|---|---|
| `references/analysis-types.md` | Once the analysis type is chosen | What to analyze, the primary question and the special rules for each of the 9 types, including how spending evidence is classified |
| `references/search-guide.md` | Before searching | Data sources per platform, search patterns, the keyword library, default searches per analysis type |
| `references/evidence-rules.md` | While collecting and judging evidence | Evidence fields, sentiment classification, clustering, trends, deduplication, evidence tiers, quotes, source priority, wording rules |
| `references/report-template.md` | Before writing the report | Report structure, the mandatory Finding / Evidence / Source table, and the final quality checklist |

## Analysis period

The primary analysis covers **January 1 of the current year through today's date**. Check today's date; never assume the year. In this skill, `[YEAR]` means the current calendar year.

- Never mix content from earlier years into the primary evidence set. Exclude older posts, videos, articles, Reddit discussions and X/Twitter posts.
- Older material may be mentioned only if genuinely necessary for context, and must be labeled **Historical Context — Not Included in [YEAR] Findings**.
- Historical material must not affect finding counts, sentiment percentages, issue rankings, trend calculations or evidence strength.
- The user may explicitly change the period (for example a patch window or a different year). Follow that, and state the period used in the methodology. Otherwise keep the restriction, including for custom analyses.
- If it is early in the year and the evidence is thin, say so in the caveats rather than quietly widening the window. You may offer the user a wider period.

## Workflow

### Step 1 — Ask for the game

Ask: **"What game would you like me to analyze?"**

Do not begin the main research until the game name is known. If the user already named the game, skip the question.

### Step 2 — Ask for the analysis type

After the game name is known, ask: **"What type of analysis would you like?"**

1. Negative Sentiment
2. Update / Patch Feedback
3. Bugs & Technical Issues
4. Missing Features / QoL
5. Monetization Feedback
6. Player Spending Impact
7. Balance / Competitive Issues
8. Event Feedback
9. Custom Analysis

Then state: **"If you don't specify, I'll default to Negative Sentiment Analysis."**

If the user does not answer the analysis-type question, automatically use Negative Sentiment Analysis. Do not repeatedly ask. If the user already stated the type in their request, skip the question.

### Step 3 — Ask for specific source links

Ask: **"Please provide the specific Reddit, YouTube, X/Twitter, Facebook, Instagram, or other public links you'd like me to scan. If you don't provide links, I'll automatically perform a general [YEAR] search across Reddit, YouTube, X/Twitter, and the web."**

Ask Steps 2 and 3 together in one message to keep the exchange short. Accepted links: Reddit posts and subreddits, YouTube videos and channels, X/Twitter posts and accounts, Facebook posts, groups and pages, Instagram posts, reels and accounts, game forums, articles, and official game or community pages.

### No-link fallback

If the user provides no links, **do not stop the analysis and do not ask for links again.** Search automatically.

- **Required:** Reddit, YouTube, X/Twitter, and the general web.
- **Also search:** Facebook and Instagram whenever relevant publicly indexed content is available.

Example: for "Analyze RAID Shadow Legends" with no links, start with *RAID Shadow Legends Reddit [YEAR]*, *YouTube [YEAR]*, *X Twitter [YEAR]*, *complaints [YEAR]*, *community feedback [YEAR]* and *update [YEAR]*, then expand the searches for the selected analysis type using `references/search-guide.md`.

### User-provided links have priority

If the user provides links:

1. Analyze those links first.
2. Run additional general searches using the game name.
3. Use the general searches to corroborate, expand or challenge the findings.
4. Do **not** restrict the research to the supplied links unless the user explicitly says **"Only analyze these links."**

Supplied sources get higher priority, but they do not block broader discovery unless the user asks for a restricted-source analysis.

## Analysis types

Adapt both the research and the report to the selected type. Load `references/analysis-types.md` for the full scope of each.

| # | Type | Primary question |
|---|---|---|
| 1 | Negative Sentiment (default) | What are players most unhappy about in [YEAR]? |
| 2 | Update / Patch Feedback | How is the community reacting to the game's [YEAR] updates? |
| 3 | Bugs & Technical Issues | What technical problems are players experiencing in [YEAR]? |
| 4 | Missing Features / QoL | What features or QoL improvements are players asking for? |
| 5 | Monetization Feedback | How does the community perceive the game's monetization? |
| 6 | Player Spending Impact | Is there credible community evidence that negative sentiment is affecting player spending behavior? |
| 7 | Balance / Competitive Issues | What balance and competitive issues are driving player dissatisfaction? |
| 8 | Event Feedback | Which events are generating positive or negative player reactions, and why? |
| 9 | Custom Analysis | The user's own question, with a methodology built for it |

## Spending guardrail

**Never add spending analysis automatically.** Include it only if the user:

- selects Player Spending Impact,
- asks whether sentiment affected spending,
- asks about purchase behavior,
- asks about F2P migration related to complaints, or
- explicitly requests revenue or spending implications.

Otherwise do not include a spending-impact section, and for non-spending analyses do not invent revenue or spending implications. A Negative Sentiment report does not analyze revenue, spending reduction, purchase refusal, F2P migration or subscription cancellation unless asked.

## Causality guardrail

Do not confuse sentiment with behavior or with business outcomes. Social-media sentiment alone cannot prove a revenue, ARPU, conversion, purchase or churn decline unless appropriate business data is available.

Use phrasing like:

- "Community evidence indicates..."
- "Players explicitly reported..."
- "The available social evidence suggests..."
- "Social evidence alone cannot establish..."

Never write "Negative sentiment caused revenue to decline" without supporting business data. Never read "I hate this update" as "this update reduced spending."

## Platform access rule

Never pretend to have accessed information that is unavailable.

- If a platform has limited indexing or access, state: *"Publicly indexed results were reviewed; platform access may limit completeness."*
- If a source cannot be opened, state: *"Source could not be independently accessed."*
- If secondary evidence exists, state: *"Secondary evidence only."*
- Never fabricate inaccessible content.

## Decision logic

- Game name missing → ask for it.
- Game name given, type missing → ask for the type; if unanswered, default to Negative Sentiment.
- Links provided → analyze them first, then run broader game-name searches (unless "Only analyze these links").
- No links → search Reddit + YouTube + X/Twitter + web automatically, and Facebook/Instagram when relevant.
- Type is Player Spending Impact → include spending-impact analysis. Any other type → do not.
- Custom analysis → follow the user's requested scope and build a suitable methodology; do not force it into the standard categories.

**Always:** restrict primary evidence to the analysis period, preserve source URLs, deduplicate evidence, produce the Finding / Evidence / Source table, state access limitations, and separate evidence from interpretation.

## Finishing

Load `references/report-template.md`, write the report in that structure, and run its final quality checklist before delivering.
