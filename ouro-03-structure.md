# OURO-03: Structure

Ouro is built to make collaboration composable.

The platform is organized into four elements — **Earth, Water, Air, Fire** — plus a few coordination primitives (Teams, Organizations) that make the elements useful in the real world.

---

## First: Everything Belongs Somewhere

### Teams are the organizing unit

Most collaborative work on Ouro happens inside **teams**:

- Team names start with `#`
- Every asset belongs to a team, so work stays discoverable
- The team page becomes a mission-focused “home” for data, tools, and discussion

If the elements are the layers of value, teams are the structure that keeps that value navigable.

---

## The Four Elements

Inspired by classical elements, Ouro organizes assets into four categories that represent different types of value:

### 🜃 Earth — Files & Datasets

Earth is the foundation: raw material that everything else builds on.

- Upload files and datasets
- Unstructured and structured data that can be queried, analyzed, and built upon
- Web UI supports rich previews for many formats (including PDF, 3D models, and molecules/crystals)

Earth assets are typically monetized via **pay-to-unlock** — a one-time fee that grants access.

*Examples: Research datasets, training data, structured databases, documents*

---

### 🜄 Water — APIs & External Tools

Water is capability: computation and transformation.

A **service** connects an external, web-accessible API to Ouro:

- Import via open standards (OpenAPI)
- Routes become callable endpoints on the platform
- Authentication can be configured so Ouro can proxy requests safely

Services can optionally declare **typed asset inputs/outputs** per route (e.g., input is a file, output is a post). That makes services more “lego-like” and easier to compose.

Water assets are typically monetized via **pay-per-use** — a cost each time the service is called.

*Examples: ML inference APIs, data processing services, generative AI tools*

---

### 🜁 Air — Posts

Ideas given form. The distribution layer.

- Write documents that embed live data, charts, and code
- Publish research that stays in sync with underlying data
- Share insights with the community
- comments and reactions for feedback loops

Posts turn assets into understanding.

Air assets are typically monetized via **pay-to-unlock** — access to the full content.

*Examples: Research papers, tutorials, analysis, blog posts*

---

### 🜂 Fire — Quests

Collective action. Problems that need solving.

- Rally the community around shared goals
- Collaborate on challenges and build together
- Optional rewards for accepted entries

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

### Python (high level)

```python
import os
from ouro import Ouro

ouro = Ouro(api_key=os.getenv("OURO_API_KEY"))

# Upload a file (Earth)
f = ouro.files.create(
    name="experiment-notes",
    description="Lab notes PDF",
    visibility="public",
    file_path="notes.pdf",
    team="#lab-team",
)

# Upload tabular data as a dataset (Earth)
import pandas as pd
df = pd.read_csv("results.csv")
ds = ouro.datasets.create(
    name="experimental-results",
    visibility="public",
    data=df,
    team="#lab-team",
)

# Publish a post that links your assets (Air)
content = ouro.posts.Editor()
content.new_header(level=1, text="Results: first pass")
content.new_paragraph(text="This post links the raw notes + the structured dataset.")
content.new_inline_asset(id=f.id, asset_type="file", view_mode="card")
content.new_inline_asset(id=ds.id, asset_type="dataset", view_mode="preview")

post = ouro.posts.create(
    title="Results: first pass",
    content=content,
    team="#lab-team",
)
```

The Python SDK enables automation, pipelines, and integration with existing tools.

---

[← Previous: Principles](ouro-02-principles.md) | [Next: Economics →](ouro-04-economics.md)
