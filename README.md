# Repolex Knowledge Graph of samuelcolvin/scolvin.com

RDF knowledge graph data for [samuelcolvin/scolvin.com](https://github.com/samuelcolvin/scolvin.com), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/scolvin.com
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fe642c11e1f465ec246aa50180b1bf956d8ab718
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fe642c11e1f465ec246aa50180b1bf956d8ab718
│           └── chunk-001.nq.gz
├── blob
│   ├── 122ae965c0bbe4981897204137f63a44421c9384.nq.gz
│   ├── 485dee64bcfb48793379b200a1afd14e85a8aaf4.nq.gz
│   ├── 8380def7cb69808a5dd3eaa615e6bf75f38c5615.nq.gz
│   └── 85f7c576b8b6ac19b9653f0f5ee2d8025469a720.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fe642c11e1f465ec246aa50180b1bf956d8ab718.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 10 files
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

[samuelcolvin/scolvin.com](https://github.com/samuelcolvin/scolvin.com)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
