# Second Brain

An LLM-maintained personal knowledge base. Raw sources go in, an organized wiki comes out.

## Folder Structure

```
second-brain/
├── AGENTS.md              # Schema — rules for how the AI manages the wiki
├── raw/                   # Drop source material here (articles, notes, PDFs, screenshots)
├── wiki/                  # AI-maintained wiki (don't edit by hand)
│   ├── INDEX.md           # Created by the AI — catalog of all wiki pages
│   └── log.md             # Created by the AI — chronological record of operations
├── outputs/               # Generated reports, briefings, answers
└── .claude/commands/      # Reusable slash commands
    ├── ingest.md
    ├── query.md
    ├── health-check.md
    └── briefing.md
```

## Slash Commands

| Command | What it does |
|---|---|
| `/ingest` | Reads all sources in `raw/`, builds or updates the wiki, reports what changed |
| `/query <question>` | Answers a question using only wiki content, saves good answers to `outputs/` |
| `/health-check` | Audits the wiki for contradictions, orphans, missing pages, and gaps |
| `/briefing <topic>` | Generates a concise briefing from wiki content |

## Inspiration

- [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f#llm-wiki) by Andrej Karpathy
- [How to Build Your Second Brain](https://x.com/NickSpisak_/status/2040448463540830705) by Nick Spisak
