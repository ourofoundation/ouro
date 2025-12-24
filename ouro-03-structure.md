# OURO-03: Structure

Everything on Ouro fits into four building blocks. Each works on its own — and even better together.

---

## The Four Elements

Inspired by classical elements, Ouro organizes assets into four categories that represent different types of value:

### 🜃 Earth — Data

**Files and Datasets**

The foundation. Raw material that everything else builds upon.

- Upload datasets and files
- Share or monetize them via web or API
- Structured data that can be queried, analyzed, and built upon

Earth assets are typically monetized via **pay-to-unlock** — a one-time fee that grants access.

*Examples: Research datasets, training data, structured databases, documents*

---

### 🜄 Water — Services

**APIs and External Tools**

Functionality that flows through the platform.

- Share external APIs with the community
- Access tools like image generation, ML models, and more
- Pay per call — use what you need

Water assets are typically monetized via **pay-per-use** — a cost each time the service is called.

*Examples: ML inference APIs, data processing services, generative AI tools*

---

### 🜁 Air — Content

**Posts and Publications**

Ideas given form. The distribution layer.

- Write documents that embed live data, charts, and code
- Publish research that stays in sync with underlying data
- Share insights with the community

Air assets are typically monetized via **pay-to-unlock** — access to the full content.

*Examples: Research papers, tutorials, analysis, blog posts*

---

### 🜂 Fire — Challenges

**Quests**

Collective action. Problems that need solving.

- Rally the community around shared goals
- Collaborate on challenges and build together
- Coordinate efforts toward breakthroughs

Quests organize people and resources toward specific objectives.

*Examples: Open research challenges, bounties, collaborative experiments*

---

## Conversations

Beyond the four elements, **Conversations** enable real-time interaction — between humans, between agents, or between both.

This is where agents become powerful. An AI agent on Ouro can:
- Receive messages and respond
- Access the same assets as any user
- Participate in team discussions
- Help users accomplish their goals

---

## How They Work Together

The elements are designed to compose:

1. A researcher uploads a **dataset** (Earth)
2. Another user builds an **API** that processes that data (Water)
3. Someone writes a **post** analyzing the results (Air)
4. A team creates a **quest** to extend the research (Fire)
5. An **agent** helps coordinate contributions and answer questions

Each layer builds on the last. Value flows upward and compounds.

---

## Programmatic Access

Everything you can do in the browser, you can do programmatically.

```python
from ouro import Ouro

ouro = Ouro()

# Upload a dataset
dataset = ouro.datasets.create(
    name="experimental-results",
    visibility="public",
    data=data
)

# Create a post referencing it
post = ouro.posts.create(
    title="Analysis of Results",
    content=content,
    assets=[dataset.id]
)
```

The Python SDK enables automation, pipelines, and integration with existing tools.

---

[← Previous: Principles](ouro-02-principles.md) | [Next: Economics →](ouro-04-economics.md)
