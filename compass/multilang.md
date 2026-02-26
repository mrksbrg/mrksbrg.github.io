---
layout: plain
title: Multi-language Evidence
---

# Multi-language Evidence: Guiding Coding Agents Beyond Python

<span style="font-size: 0.85em; opacity: 0.7;">
<a href="/compass/">Back to overall page</a>
</span>

This page provides supporting evidence that the value of using <a href="/compass/#codehealth">CodeHealth</a> as a compass for coding agents generalizes beyond Python.

For this series of experiments, we deployed a self-hosted instance of the open-source coding agent [gptme](https://gptme.org/) on infrastructure equipped with NVIDIA A100 GPUs. On the same server, the agent used Qwen3-Coder-30b as the underlying LLM. This is the strongest medium-sized model we have worked with and, critically, it supports *tool calling* and integration with the CodeScene MCP server. For each file, the agent was allowed up to 50 refactoring iterations.

## Test pass rate as a function of CodeHealth

<figure id="fig-gptme-results">
  <img src="gptme-results.png"
       alt="gptme with MCP"
       style="max-width: 100%; display: block; margin: 1.5em auto;">
  <figcaption style="font-size: 0.9em; opacity: 0.75; text-align: center;">
    <strong>Figure 1.</strong>
    gptme with Qwen3 and CodeHealth guidance via MCP.
  </figcaption>
</figure>

### Takeaways

- **The relationship between CodeHealth and refactoring reliability generalizes across languages** once CodeHealth exceeds approximately 7.
- **Agentic refactoring is most effective for Python**, slightly less so for Java, while **C++ is more challenging**.
- **Explicit CodeHealth guidance helps keep even a less capable agent on track**, as indicated by the predominantly dark-blue markers corresponding to meaningful code smell removal.

## File-level refactoring results

Each horizontal line represents the **CodeHealth journey of a single file**, sorted vertically by their original CodeHealth:
- **Green** lines indicate files whose CodeHealth improved; line length reflects the magnitude of improvement.
- **Purple** lines indicate files that reached a perfect CodeHealth score of 10.
- **Red** lines indicate files whose CodeHealth decreased.
- **White gaps** correspond to files whose CodeHealth remained unchanged.
- **Black points** mark refactorings that did not pass the test suite.

<figure id="fig-gptme-details">
  <img src="gptme-details.png"
       alt="Detailed refactoring results with gptme"
       style="max-width: 100%; display: block; margin: 1.5em auto;">
  <figcaption style="font-size: 0.9em; opacity: 0.75; text-align: center;">
    <strong>Figure 2.</strong>
    Detailed results from refactoring with gptme guided by CodeHealth. Note that the apparent bumps in the C++ and Java plots are effects of the file sampling strategy.
  </figcaption>
</figure>

### Takeaways

- **Python shows the strongest outcomes**: gptme frequently removes all detected code smells, as indicated by purple lines.
- **Java exhibits more conservative improvements**: fewer files reach a perfect CodeHealth score, but decreases in CodeHealth (red) are typically smaller in magnitude.
- **C++ presents the most mixed results**: only 52% of refactored files pass the test suite, and CodeHealth changes span a wide range in both positive and negative directions.
 
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
           style="height: 54px; vertical-align: middle; margin-right: 16px;">
    </a>

    <a href="https://www.vinnova.se/en/p/codehealth-as-the-true-north-for-coding-agents/"
       target="_blank" rel="noopener">
      <img src="/assets/img/vinnova.svg"
           alt="Vinnova logo"
           style="height: 32px; vertical-align: middle;">
    </a>
  </div>
</div>