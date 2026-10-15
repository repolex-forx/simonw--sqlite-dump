# Repolex Knowledge Graph of simonw/sqlite-dump

RDF knowledge graph data for [simonw/sqlite-dump](https://github.com/simonw/sqlite-dump), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/sqlite-dump
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 14655bedf4e99eaae9a60ffac2223c0e846f4684
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 14655bedf4e99eaae9a60ffac2223c0e846f4684
│           └── chunk-001.nq.gz
├── blob
│   ├── 22571b129f5f6a99d3ba9f66cfc0eb48158c5b00.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4565f5d355b500d313d56635dd8692249a6d19a8.nq.gz
│   ├── 53605b7a5ec51bc95dca4fb43fdb350bf9362435.nq.gz
│   ├── 5b707703e8f1d5d2a2d1ad2d3351d83e8e6465cd.nq.gz
│   ├── b7b5e5ddc0ae8fb6478bd6da4460bf768a1f3e1f.nq.gz
│   ├── daded6c215c4eb2e67e3a6bc9c9edec767e0c2c2.nq.gz
│   └── f65656da175887e4ee68d56a26a379c1f8821113.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 14655bedf4e99eaae9a60ffac2223c0e846f4684.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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

[simonw/sqlite-dump](https://github.com/simonw/sqlite-dump)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
