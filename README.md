# Single-Brand Deep Dive

[English](README.md) | [简体中文](README.zh-CN.md)

> Build a full-dimension data profile for one brand, one shop or one personal IP, and render it three ways from a single data source.

## What this is

This is not a region-wide inventory. Its sibling project `local-wanghong-audit` answers "what exists in this area". This one answers a narrower and harder question: what is actually going on with this one thing.

The work starts with a feasibility check, not with data collection. Most of the interesting numbers people ask for — total volume across platforms, a yearly interest index, exact review counts — are simply not exposed at the product level. Finding that out in five minutes is cheaper than producing a confident report built on proxies nobody agreed to.

## Why we open-sourced it

We kept running into the same conversation: someone asks for a data profile of a brand, and the honest answer involves explaining what cannot be measured before saying what can.

So we wrote the procedure down, including the boundary part. What makes it shareable is precisely that it is generic — the checklist of what each platform exposes is useful regardless of who is doing the research, and it contains none of our own analysis.

## What it does

- **Feasibility check first.** A documented pass over what each platform actually exposes through its interface, before any metric is committed to.
- **Honest substitution.** Where a number is unavailable, the alternative metric is chosen explicitly and the substitution is stated in the deliverable.
- **Reproducible keyword frequency.** A purpose-built Chinese n-gram implementation, so the term counts can be re-derived rather than taken on trust.
- **One source, three renders.** The HTML dashboard, Word report and Excel ledger are generated from the same dataset, so the formats cannot disagree.
- **Source-linked claims.** Findings carry their evidence, and unsupported statements are marked as such.

## Requirements

Python 3

## Installation

```bash
git clone https://github.com/<your-username>/single-brand-deep-dive.git
```

Then place the folder into your agent skills directory:

| OS | Path |
|---|---|
| Windows | `C:\Users\<you>\.workbuddy\skills\single-brand-deep-dive\` |
| macOS / Linux | `~/.workbuddy/skills/single-brand-deep-dive/` |

There is no build step. Restart the session and it takes effect.

## How to use

Name the object and what you want to know:

- "Build a data profile for <brand>"
- "How much buzz is there around <shop>, and what are people saying"
- "Why did <brand> get popular, and is it still trending"

Expect the skill to start with what it can and cannot obtain. That first pass is the point, not an obstacle.

## Files

```
└── SKILL.md
```

## Notes and limits

1. **Platform interfaces are the ceiling, not the method.** If an interface does not expose a number, no amount of cleverness retrieves it. The repository says so plainly.
2. **Keyword frequency is descriptive, not interpretive.** Term counts show what appears; deciding what it means is still a judgement call.
3. **Small samples distort ratios.** A brand with thirty mentions and a brand with thirty thousand should not be compared on the same scale.
4. **Review counts are often unavailable in bulk.** Platforms surface a display number, not a retrievable dataset.

## License

MIT
