---
layout: plain
title: CodeHealth and Coding Agents
---

# CodeHealth as a Prerequisite and Compass for Coding Agents

<span style="font-size: 0.85em; opacity: 0.7;">
<a href="https://codescene.com/">CodeScene</a> research direction maintained by <a href="https://mrksbrg.com/">Dr. Markus Borg</a>
</span>

**Thesis:** High-quality code has never been more important than in the AI era.

**First,** healthy code is more AI-friendly: it is easier for coding agents to analyze, modify, and extend without introducing unintended side effects.

**Second,** as the volume of code grows, human readability becomes increasingly critical. The future will be *hybrid*, and humans will continue to read, review, and reason about code -- precisely when it matters most.

<div class="callout">
  <strong><a href="#codehealth">CodeHealth</a> acts as a compass for both humans and coding agents, helping ensure that code remains maintainable over time.</strong>
</div>

---

## Code quality is a prerequisite for successful agent deployment

We studied refactoring success as a proxy for how effectively AI systems can work with code of varying quality ([FORGE 2026, arXiv preprint]). Across our experiments, large language models consistently perform better when operating on healthier code.

The figure below shows test pass rates as a function of CodeHealth when LLMs are prompted to *improve maintainability in Python files*. For reference, Claude Code pinned to Sonnet 4.5 is shown alongside other models (brown curve). The color of each data point indicates the fraction of refactorings that removed at least one code smell, conditional on passing tests.

![LLM refactoring success vs. CodeHealth](llm-friendliness_vs_codehealth.png)

### Takeaways

- **Higher CodeHealth decreases refactoring risk** across all evaluated models.
- **The trend is consistent across model classes**, from medium-sized open models to state-of-the-art Sonnet 4.5.
- **As CodeHealth increases, LLMs identify fewer code smells to remove**, reflecting a shift toward more cosmetic changes.
- **Claude exhibits the most conservative behavior**: the lighter blue markers reveal that many test-passing refactorings involve limited structural change (reported in related work ([MSR 2026, arXiv PDF]))

<div class="callout">
  <strong>A healthy codebase substantially increases the likelihood of succesful coding agent deployment.</strong>
</div>

[FORGE 2026, arXiv preprint]: https://arxiv.org/abs/2601.02200
[MSR 2026, arXiv PDF]: https://arxiv.org/pdf/2601.20160

---

## Coding agents need CodeHealth guidance

Giving agents access to CodeHealth using the MCP makes wonders.

![Uplift from using Claude with CodeHealth compass](claude-mcp.png)

---

## <a id="codehealth"></a>What is CodeHealth™?

CodeHealth is a code quality metric that aligns with how engineers perceive maintainability. Peer-reviewed research shows that higher CodeHealth is associated with outcomes that matter for software-intensive organizations.
- **Healthy code** is associated with, on average, **15× fewer defects**, **2× faster feature implementation**, and **10× lower uncertainty in task completion**  
  ([TechDebt 2022, arXiv preprint])
- **CodeHealth provides a shared language** for discussing the business impact of code quality with executive stakeholders  
  🏆 *Best Paper Award*  ([TechDebt 2024, arXiv preprint])
- **CodeHealth outperforms established alternatives**, performing **6× better than SonarQube’s metric** on a public benchmark and outperforming the traditional **Maintainability Index**  
  ([ICSME 2024, arXiv preprint])

[TechDebt 2022, arXiv preprint]: https://arxiv.org/abs/2203.04374
[TechDebt 2024, arXiv preprint]: https://arxiv.org/abs/2401.13407
[ICSME 2024, arXiv preprint]: https://arxiv.org/abs/2408.10754v1

---

<div style="margin-top: 3em; font-size: 0.85em; opacity: 0.7;">
  This research was conducted at CodeScene and Lund University with support from Vinnova, Sweden’s Innovation Agency.
  <br/><br/>

  <div style="text-align: center;">
    <a href="https://codescene.com/" target="_blank" rel="noopener">
      <img src="/assets/img/codescene.png"
           alt="CodeScene logo"
           style="height: 42px; vertical-align: middle; margin-right: 16px;">
    </a>

    <a href="https://www.lu.se/" target="_blank" rel="noopener">
      <img src="/assets/img/unilund.png"
           alt="Lund University logo"
           style="height: 42px; vertical-align: middle; margin-right: 16px;">
    </a>

    <a href="https://www.vinnova.se/en/p/codehealth-as-the-true-north-for-coding-agents/"
       target="_blank" rel="noopener">
      <img src="/assets/img/vinnova.svg"
           alt="Vinnova logo"
           style="height: 42px; vertical-align: middle;">
    </a>
  </div>
</div>

