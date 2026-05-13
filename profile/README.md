<p align="center">
  <a href="https://github.com/opendb-ai/openDB">
    <img src="https://raw.githubusercontent.com/opendb-ai/official-web/main/assets/opendb-icon.svg" alt="OpenDB" width="72" />
  </a>
</p>

<h1 align="center">OpenDB</h1>

<p align="center">
  <strong>The local database for AI agents.</strong><br/>
  Read any file. Search every workspace. Remember long-term context.
</p>

<p align="center">
  <a href="https://github.com/opendb-ai/openDB">OpenDB</a>
  ·
  <a href="https://github.com/opendb-ai/official-web">Website</a>
  ·
  <a href="https://github.com/opendb-ai/openDB/blob/main/docs/agent-protocol.md">Agent protocol</a>
  ·
  <a href="https://pypi.org/project/open-db/">PyPI</a>
</p>

---

## Three Lines To Give Your Agent Memory

```bash
pip install open-db[cli]
opendb index ./my_workspace
opendb serve-mcp
```

OpenDB gives any MCP-compatible agent a private, local database for files, search, and memory. It can read PDFs, Word documents, spreadsheets, presentations, code, text, and images; search across workspaces; store and recall durable memories; and switch projects at runtime.

## Why It Exists

Agents waste too much context and time writing one-off parsing scripts, scanning entire folders, and re-learning facts from previous sessions. OpenDB makes the simple path fast:

- **Local-first**: SQLite by default, Postgres when shared access matters.
- **Zero embeddings required**: SQLite FTS5 and Postgres `tsvector` before vector infrastructure.
- **MCP native**: twelve tools for read, search, glob, memory, and workspace switching.
- **Long-term memory**: semantic facts, dated episodes, reusable procedures, pinned context, and recency-aware recall.
- **File-native**: structured output for pages, rows, slides, code lines, and document chunks.

## Benchmark Signals

| Metric | OpenDB |
| --- | ---: |
| LongMemEval_S R@5 | **98.5%** |
| LongMemEval_S R@10 | **99.1%** |
| Median memory recall | **3.0 ms** |
| Token savings vs command parsing | **55-73%** |
| Embedding calls for retrieval | **0** |

Full methodology lives in the [benchmark report](https://github.com/opendb-ai/openDB/blob/main/benchmark/REPORT.md).

## Built For Agent Workflows

OpenDB is designed around a simple protocol:

1. Check local files and memories before external search.
2. Read the smallest useful page, row, slide, or line range.
3. Store durable memories carefully, with provenance and type.
4. Keep the runtime boring: deterministic indexing, timestamps, FTS, and small schemas.

Start with [AGENTS.md](https://github.com/opendb-ai/openDB/blob/main/AGENTS.md) or the fuller [agent protocol](https://github.com/opendb-ai/openDB/blob/main/docs/agent-protocol.md).

## Repositories

| Repository | Description |
| --- | --- |
| [openDB](https://github.com/opendb-ai/openDB) | Core database, MCP server, CLI, parsers, memory service, and benchmarks. |
| [official-web](https://github.com/opendb-ai/official-web) | Static official website for OpenDB. |
| [.github](https://github.com/opendb-ai/.github) | Organization profile and shared GitHub metadata. |

## Design Bias

OpenDB stays useful without an embedding API. Prefer deterministic indexing, full-text search, timestamps, provenance, and small schemas before adding new infrastructure.
