# Tombstoning Tool Calls

A demonstration of "tombstoning" - a technique for compressing verbose AI tool call outputs into concise summaries, reducing token consumption by ~94%.

## The Concept

When AI models use tools, they often generate lengthy outputs that bloat conversation history. Tombstoning solves this by replacing verbose tool results with compact summaries after their first use.

**The Result**: From 441 tokens down to 26 tokens - a 94% reduction.

## Two Approaches

### 1. Naive Tombstoning
Manually replace long outputs with short, hand-written summaries.

```python
# Original: 441 tokens of detailed horoscope
# Tombstoned: "You will have good fortune" (22 tokens)
```

### 2. LLM-Derived Tombstoning
Use a lightweight model (like GPT-5-nano) to automatically summarize outputs.

```python
# Original: 441 tokens
# LLM Summary: "Virgo: transformative week; trust intuition." (26 tokens)
```

## When It Matters

- **5 tool calls**: Save ~2,000 tokens per conversation
- **Long-running agents**: Dramatically reduce context window usage
- **Storage & caching**: Store 20x more conversation history

## The Tradeoff

Tombstoning is about finding balance: preserve enough context for the conversation to continue meaningfully, while discarding verbose details that aren't needed after initial use.

---

*Inspired by the [Anthropic podcast on YouTube](https://www.youtube.com/watch?v=XuvKFsktX0Q)*
