# Writing & Analysis: Reports, Summaries & Data Interpretation

## Prompt 1 — Executive Summary from Raw Data

**Best with**: Claude, GPT-4, Gemini

```
You are a senior analyst preparing a briefing for non-technical executives. I will provide raw data or a detailed report.

Transform it into an executive summary following this structure:
1. **Bottom line up front** (1 sentence — the single most important takeaway)
2. **Key findings** (3-5 bullet points, each under 20 words)
3. **What changed** (compared to last period / baseline — better, worse, or flat)
4. **Risk or opportunity** (one thing that needs attention)
5. **Recommended action** (one specific next step, not vague advice)

Rules:
- No jargon. If a technical term is necessary, define it in parentheses.
- Use concrete numbers, not "significant increase" — say "23% increase"
- Total length: under 250 words
- Tone: confident and direct, not hedging

Data:
[PASTE DATA OR REPORT HERE]
```

**Why it works**: "Bottom line up front" mirrors military/consulting briefing format. Word limits and "no jargon" constraints force clarity. "Not vague advice" in the action item prevents generic recommendations.

**Variations**:
- Change audience: "preparing for a board meeting" vs "for the engineering team"
- Add "Include a comparison table" for data-heavy summaries
- Add "Highlight anything that contradicts our assumptions" for critical analysis

---

## Prompt 2 — Research Synthesis

**Best with**: Claude, GPT-4

```
I have multiple sources about [TOPIC]. Synthesize them into a single coherent analysis.

For each source I provide, extract:
- Core claim or finding
- Methodology or evidence quality (strong/moderate/weak)
- Any bias or limitations

Then produce:
1. **Consensus view**: what do most sources agree on?
2. **Disagreements**: where do sources conflict, and why?
3. **Gaps**: what questions remain unanswered across all sources?
4. **My take**: based on evidence quality, which position is best supported?

Do not just summarize each source sequentially. I want cross-source analysis — compare and contrast, find patterns, identify contradictions.

Sources:
[PASTE SOURCES HERE]
```

**Why it works**: "Do not just summarize sequentially" is the key constraint — without it, models default to source-by-source summaries. Asking for evidence quality assessment forces critical thinking.

**Variations**:
- Add "Weight peer-reviewed sources higher than blog posts" for academic contexts
- Add "Flag any claims that could be outdated given the current date" for fast-moving fields
- Add "Output as a comparison matrix (table)" for visual comparison
