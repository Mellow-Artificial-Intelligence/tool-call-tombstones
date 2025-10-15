# Tombstoning Tool Calls

A demonstration of "tombstoning" - a technique for compressing verbose AI tool call outputs into concise summaries, reducing token consumption by > 95%.

## The Concept

When AI models use tools, they often generate lengthy outputs that bloat conversation history. Tombstoning solves this by replacing verbose tool results with compact summaries after their first use.

**The Result**: From 679 tokens down to 13 tokens - a 98% reduction.

## The Approach: LLM-Derived Tombstoning

Use a lightweight model (like GPT-5-nano) to automatically summarize tool outputs into 5 words or less.

```python
# Original: 679 tokens of detailed customer profile
# Tool Output: Full CRM profile with engagement history, purchase data, support metrics...

# LLM Summary: "VP Eng at premium SaaS." (13 tokens)
```

## When It Matters

- **5 tool calls**: Save ~3,300 tokens per conversation
- **Long-running agents**: Dramatically reduce context window usage
- **Storage & caching**: Store 50x more conversation history

## The Tradeoff

Tombstoning is about finding balance: preserve enough context for the conversation to continue meaningfully, while discarding verbose details that aren't needed after initial use.

---

*Inspired by the [Anthropic podcast on YouTube](https://www.youtube.com/watch?v=XuvKFsktX0Q)*
