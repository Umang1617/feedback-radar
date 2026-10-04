# 📡 Feedback Radar

**Find out what players are really saying about a game, with every finding backed by a dated, linked source.**

![Agent Skill](https://img.shields.io/badge/Agent_Skill-SKILL.md-6C47FF?style=flat-square)
![Analysis types](https://img.shields.io/badge/Analysis_types-9-2EA44F?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

Feedback Radar is an agent skill (a `SKILL.md` plus four reference files). Give it a game and it analyzes public community feedback from Reddit, YouTube, X/Twitter, Facebook, Instagram, forums and the web. It then writes a structured report with sentiment, ranked issues, platform-by-platform evidence and a mandatory Finding / Evidence / Source table.

It is built to be auditable: no invented quotes, no pretending to read pages it couldn't open, no leaps from "players are angry" to "revenue dropped".

<!-- TODO: add a screenshot or a sample report here -->

---

## Try it

> Analyze RAID Shadow Legends
>
> What are players unhappy about in Genshin Impact? Focus on bugs.
>
> How did players react to the latest Brawl Stars update?

The skill asks for the game, then the analysis type, then any specific links you want scanned. If you skip the type it defaults to negative sentiment. If you give no links it searches Reddit, YouTube, X/Twitter and the web on its own, and checks Facebook and Instagram when public content is available.

## Nine analysis types

| # | Type | Answers |
|---|---|---|
| 1 | **Negative Sentiment** (default) | What are players most unhappy about? |
| 2 | **Update / Patch Feedback** | How is the community reacting to recent updates? |
| 3 | **Bugs & Technical Issues** | What technical problems are players experiencing? |
| 4 | **Missing Features / QoL** | What improvements are players asking for? |
| 5 | **Monetization Feedback** | How does the community perceive the monetization? |
| 6 | **Player Spending Impact** | Is there credible evidence that sentiment affects spending? |
| 7 | **Balance / Competitive Issues** | What balance problems are driving dissatisfaction? |
| 8 | **Event Feedback** | Which events are loved or hated, and why? |
| 9 | **Custom Analysis** | Your own research question |

## What the report contains

Title, executive summary, objective, methodology (sources, period, keywords, counts, access limits), overall findings, sentiment, top issues, evidence per platform, the **Finding / Evidence / Source table**, a section specific to the analysis type, a product assessment, recommendations tied to the evidence, and caveats.

## Principles it follows

- **Current-year focus.** The primary evidence covers January 1 of the current year to today. Older material appears only as clearly labeled historical context and never affects counts or rankings. You can ask for a different period.
- **Spending is opt-in.** It only analyzes spending when you ask for it, and then it separates explicit evidence (a player says they stopped buying) from indirect signals.
- **No overreach.** Social sentiment alone can't prove revenue, conversion or churn changes, and the report says so.
- **Honest about access.** If a post can't be opened, it says "Source could not be independently accessed" and never invents it.
- **Evidence tiers and deduplication.** Weak, single-complaint evidence is labeled as weak, and reposts or syndicated articles are counted once.

## Install

**Claude Code and compatible agents.** Clone the repo straight into your skills folder:

```bash
git clone https://github.com/Umang1617/feedback-radar.git ~/.claude/skills/feedback-radar
```

**Other agents.** Copy `SKILL.md` and the `references/` folder into a folder named `feedback-radar` inside wherever your agent loads skills from, or upload the packaged skill file where skill uploads are supported.

The agent needs web search and page-reading tools. The skill needs no API keys, accounts or logins.

## Make it yours

| To change | Edit |
|---|---|
| Workflow, guardrails, analysis period | `SKILL.md` |
| What each analysis type covers | `references/analysis-types.md` |
| Platforms, search patterns, keywords | `references/search-guide.md` |
| Evidence tiers, sentiment classes, wording rules | `references/evidence-rules.md` |
| Report sections and the final checklist | `references/report-template.md` |

## Repo contents

```
feedback-radar/
├── SKILL.md                      # workflow, guardrails, decision logic
├── references/
│   ├── analysis-types.md         # the 9 analysis types
│   ├── search-guide.md           # sources, searches, keyword library
│   ├── evidence-rules.md         # how evidence is collected and judged
│   └── report-template.md        # report structure and quality checklist
├── README.md
├── LICENSE
└── .gitignore
```

## Good to know

- **Social data is a sample, not a poll.** The report describes what is visible in public discussions it could reach, not what all players think.
- **Platform access varies.** X/Twitter, Facebook and Instagram often limit what search can see. The report states these limits.
- **Reports quote public posts.** Check each platform's terms of use and your own policies before sharing a report, and avoid singling out individual players.
- **Third-party names.** Game, website and platform names belong to their owners. This project is not affiliated with or endorsed by any of them.

## Roadmap

- [ ] Side-by-side comparison of two games
- [ ] Optional export of the evidence table to CSV
- [ ] A short report mode for quick scans

## Credits

Built by [Umang Srivastava](https://www.linkedin.com/in/umang1617/).

## License

[MIT](LICENSE)
