# Repolex Knowledge Graph of deepset-ai/spring-into-haystack

RDF knowledge graph data for [deepset-ai/spring-into-haystack](https://github.com/deepset-ai/spring-into-haystack), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download deepset-ai/spring-into-haystack
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 33743038970236c920d539483d31d1b9e53b0b40
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 33743038970236c920d539483d31d1b9e53b0b40
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a197900e25d259ab4af2e31e78501787d7a6daa.nq.gz
│   ├── 1ff7648ef67d40a219dcc96ffcf5da8981d99297.nq.gz
│   ├── 3164a9d2dae83d3ba9e02ca3ac5bc790ed293fc6.nq.gz
│   ├── a7285a0dd8488fd350ce6bb00940d7ac4fdd334a.nq.gz
│   ├── c33499b6eff8be581989be7146827a74cda635ec.nq.gz
│   ├── d381e2c8b90972003147970dc4f168c54f503273.nq.gz
│   └── d72d8dd31e51ae2524546c622a2f4c72b99cb0fb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 33743038970236c920d539483d31d1b9e53b0b40.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[deepset-ai/spring-into-haystack](https://github.com/deepset-ai/spring-into-haystack)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
