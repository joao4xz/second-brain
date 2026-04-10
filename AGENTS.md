# Knowledge Base Schema

## What This Is

A personal knowledge base — an LLM-maintained second brain. Raw sources go in, organized wiki comes out.

## How It's Organized

- `raw/` contains unprocessed source material (articles, notes, screenshots, PDFs). Never modify these files.
- `wiki/` contains the organized wiki. AI maintains this entirely. Humans read it; the AI writes it.
- `wiki/INDEX.md` is a catalog of every wiki page with a one-line description, organized by category.
- `wiki/log.md` is an append-only chronological record of all operations (ingests, queries, health checks).
- `outputs/` contains generated reports, answers, briefings, and analyses.

## Wiki Rules

- Every topic gets its own `.md` file in `wiki/`.
- Every wiki file starts with a one-paragraph summary.
- Link related topics to each other using `[[topic-name]]` format.
- Maintain an `INDEX.md` in `wiki/` that lists every topic with a one-line description.
- When new raw sources are added, update all relevant wiki articles — not just the new one.
- Note contradictions explicitly when sources disagree.

## Logging

Every operation (ingest, query, health check, briefing) must append an entry to `wiki/log.md` with the format:
`## [YYYY-MM-DD] operation | Brief description`

## Ingest Workflow

1. Read the new source(s) in `raw/`.
2. Create or update `wiki/INDEX.md` first.
3. Create one `.md` file per major topic extracted.
4. Link related topics across wiki pages.
5. Summarize every source referenced.
6. If a topic already has a wiki page, update it rather than creating a duplicate.

## Query Workflow

1. Read `wiki/INDEX.md` to find relevant pages.
2. Read the relevant wiki pages.
3. Synthesize an answer grounded in the wiki content.
4. Save valuable answers to `outputs/` as markdown files.
5. If the answer reveals new insights or connections, integrate them back into the relevant wiki pages and update `wiki/INDEX.md` if needed. Knowledge should compound in the wiki, not stay isolated in `outputs/`.

## Health Check Workflow

1. Review the entire `wiki/` directory.
2. Flag contradictions between articles.
3. Find topics mentioned but never explained (missing pages).
4. List claims not backed by a source in `raw/`.
5. Identify orphan pages with no inbound links.
6. Suggest new articles that would fill gaps.
