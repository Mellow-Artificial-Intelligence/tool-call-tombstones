# Tool Call Tombstones

a technique for compressing verbose AI tool call outputs into concise summaries, reducing token consumption.

## The Concept

When AI models use tools, they often generate lengthy outputs that bloat conversation history. We attempt to solve this by replacing verbose tool results with compact summaries after their first use.

**The Result**: From ~600 tokens down to less than 20 tokens.

## The Approach:

Use a lightweight model (like GPT-5-nano) to automatically summarize tool outputs into 5 words or less.

```python
# Original: ~600 tokens of detailed customer profile
# Tool Output: Full CRM profile with engagement history, purchase data, support metrics...

# LLM Summary: "VP Eng at premium SaaS."
```

## When It Matters

- **Lots of tool calls**: Save tons of tokens per conversation
- **Long-running agents**: Dramatically reduce context window usage
- **Storage & caching**: Store more conversation history

## The Tradeoff

There is a balance to be found: preserve enough context for the conversation to continue meaningfully, while discarding verbose details that aren't needed after initial use.

---

*Inspired by the [Anthropic podcast on YouTube](https://www.youtube.com/watch?v=XuvKFsktX0Q)*
