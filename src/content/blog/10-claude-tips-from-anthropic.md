---
title: "10 Game-Changing Claude Tips from Anthropic's Alex Albert"
description: "Learn the best practices for using Claude AI from Alex Albert, Anthropic's Head of Developer Relations. Discover powerful techniques including XML tags, extended thinking, multi-agent systems, and more."
pubDate: 2026-01-08
tags: ['AI', 'Claude', 'productivity', 'tips']
---

# 10 Game-Changing Claude Tips from Anthropic's Alex Albert

If you're using Claude AI, you might be leaving serious capabilities on the table. [Alex Albert](https://x.com/alexalbert__), Anthropic's Head of Developer Relations, has been sharing invaluable insights on how to get the most out of Claude. Here are 10 powerful tips that will transform how you work with AI.

## 1. Structure Your Prompts with XML Tags

One of the most impactful techniques is using XML tags to structure your prompts. Tags like `<instructions>`, `<example>`, and `<context>` help Claude clearly separate different parts of your request.

**Why it works:** XML tags prevent Claude from mixing up instructions with examples or context. There are no "canonical" tags Claude was specifically trained on—it responds well to any logical tag names.

**Example:**

```xml
<instructions>
Write a Python function to calculate fibonacci numbers
</instructions>

<requirements>
- Use recursion
- Add memoization for efficiency
- Include docstrings
</requirements>
```

Combining XML tags with techniques like few-shot examples (`<examples>`) or chain of thought (`<thinking>`, `<answer>`) creates super-structured, high-performance prompts.

[Source: Claude Documentation on XML Tags](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/use-xml-tags)

## 2. Unlock Extended Thinking for Complex Tasks

Claude's extended thinking mode is a game-changer for difficult problems. When enabled, Claude takes time to reason through requests step-by-step, showing you its thinking process.

**How to use it:** In Claude Code, simply use the word "think" to trigger extended thinking with increasing levels:

- `think` < `think hard` < `think harder` < `ultrathink`

Each level allocates progressively more thinking budget. Start at the minimum (1,024 tokens) and increase incrementally to find the optimal range.

**Best for:** Math, coding, complex analysis, and any task requiring step-by-step reasoning.

[Source: Claude Extended Thinking Documentation](https://docs.claude.com/en/docs/build-with-claude/extended-thinking)

## 3. Leverage Project Knowledge for Context

Upload documents to Claude Projects to create persistent knowledge that Claude can reference. This is like giving Claude a specialized knowledge base for your specific use case.

**Alex Albert's tip:** "Extended thinking works best when Claude already has context—it's about contextual thinking. Context → think → execute = significantly better results."

**Use cases:**

- Code documentation for your project
- Company guidelines and standards
- Research papers or technical specs
- Previous conversation summaries

[Source: Claude Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)

## 4. Command an Army: Multi-Agent Claude Code

Alex Albert noted that using Git worktrees to run multiple Claude Code instances in parallel "Legitimately feels like commanding an army of software engineers."

**How it works:**

- Use `git worktree` to create separate working directories
- Spin up multiple Claude Code instances
- Each instance works on different parts of your project simultaneously
- Avoid conflicting changes on the same codebase

**The result:** Tackle different features, bugs, or refactors in parallel, dramatically speeding up development.

[Source: Alex Albert on X](https://x.com/alexalbert__/status/1979577547575951616)

## 5. Start with the Best, Then Optimize

When selecting which Claude model to use, Alex Albert recommends a specific framework:

**The strategy:** "Start with Opus and keep iterating with prompt engineering until Opus is hitting your bar—then move on to testing Sonnet and Haiku."

**Why this matters:**

- Ensures you're not under-scoping what's possible
- You optimize your prompts with the smartest model first
- Then you can cost-optimize by testing cheaper models
- Prevents the trap of thinking a task is impossible when you just need better prompts

[Source: Alex Albert on Model Selection](https://x.com/alexalbert__/status/1775588774518665613)

## 6. Master Artifacts for Interactive Content

Artifacts are specialized containers for significant content you might want to reference, modify, or reuse—including complete applications and interactive tools.

**What Claude excels at with Artifacts:**

- Interactive visualizations (charts, graphs, SVG graphics)
- Complete code programs
- Web-based data visualizations
- Tools that solve specific problems

**Alex Albert's discovery:** Using the canvas-design skill, Claude created PDF visuals entirely through code—"I had no clue this was possible before."

[Source: Claude Artifacts Best Practices](https://max-productive.ai/ai-tools/claude/)

## 7. Research and Plan Before Coding

This tip dramatically improves coding outcomes. Without explicit planning, Claude tends to jump straight into implementation.

**The technique:** Ask Claude to research and plan first:

```
Before writing code, please:
1. Research the best approach for this problem
2. Outline your implementation plan
3. Identify potential edge cases
4. Then implement the solution
```

**Internal benchmarks show:** This approach significantly improves code quality and reduces bugs.

[Source: Claude Code Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)

## 8. Use /clear to Manage Context Window

During long sessions, Claude's context window can fill with irrelevant conversation, reducing performance and causing Claude to lose focus.

**The fix:** Use the `/clear` command frequently between tasks to reset the conversation while maintaining your project knowledge.

**When to clear:**

- After completing a task
- When switching to a different topic
- If you notice Claude's responses becoming less relevant
- Before starting a new complex task

This simple habit maintains peak performance throughout your session.

[Source: Claude AI Review 2025](https://max-productive.ai/ai-tools/claude/)

## 9. Configure Projects with CLAUDE.md

Claude Code automatically checks for a `CLAUDE.md` file in your project's root directory. If found, its contents are included in every context.

**What to include:**

- Project overview and architecture
- Coding standards and conventions
- Important gotchas or constraints
- Build and test commands
- Common patterns used in the codebase

**Best practice:** Keep these files concise and human-readable. Think of it as onboarding documentation that both humans and Claude can use.

[Source: Anthropic Engineering Blog](https://www.anthropic.com/engineering/claude-code-best-practices)

## 10. Unlock Interleaved Thinking for Agents

Claude 4 models support interleaved thinking, enabling Claude to think between tool calls and reason after receiving tool results.

**Why this matters for agentic workflows:**

- Claude can analyze tool outputs before deciding next steps
- More sophisticated reasoning in multi-step tasks
- Better decision-making in complex automation

**How to enable:** Add the beta header `interleaved-thinking-2025-05-14` to your API request.

**Alex Albert on multi-agent systems:** "Multi-agent systems are the next frontier of AI applications. We've found they beat single agents by up to 90%+ on some complex tasks."

[Source: Claude Extended Thinking Features](https://docs.claude.com/en/docs/build-with-claude/extended-thinking)

## Bonus: How Alex Albert Uses Claude Daily

Alex shared how Anthropic employees use Claude:

- **Meeting summaries:** Transcribe Google Meet calls and ask Claude to summarize conversations, action items, and next steps
- **Project management:** Uses Claude with Asana integration to translate PRDs into to-dos for engineers
- **Engineering work:** Claude Code is used for working on claude.ai itself, fixing pull requests, spinning up scripts, and working in Jupyter Notebooks

The key insight? The team building Claude uses it extensively for their own work—that's how you know it's powerful.

[Source: Time Interview with Alex Albert](https://time.com/charter/7296299/how-anthropic-uses-its-own-technology/)

## Conclusion

These tips come from the people who know Claude best. Whether you're using Claude for coding, writing, analysis, or creative work, these techniques will help you unlock capabilities you didn't know existed.

**Start with these three:**

1. Structure your prompts with XML tags
2. Enable extended thinking for complex tasks
3. Create a CLAUDE.md file for your projects

Then gradually incorporate the other techniques as you become more comfortable. The difference in output quality and capability is remarkable.

---

_Have you discovered other powerful Claude techniques? I'd love to hear about them—reach out on [LinkedIn](https://linkedin.com/in/majidbabaeifar) or [email me](mailto:majidbabaeifar@gmail.com)._

## Sources

- [Alex Albert on X/Twitter](https://x.com/alexalbert__)
- [Claude Documentation - Extended Thinking](https://docs.claude.com/en/docs/build-with-claude/extended-thinking)
- [Claude Documentation - XML Tags](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/use-xml-tags)
- [Anthropic Engineering - Claude Code Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)
- [Time - How Anthropic Uses Its Own Technology](https://time.com/charter/7296299/how-anthropic-uses-its-own-technology/)
- [Claude AI Review 2025](https://max-productive.ai/ai-tools/claude/)
