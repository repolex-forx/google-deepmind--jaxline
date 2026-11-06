# Repolex Knowledge Graph of google-deepmind/jaxline

RDF knowledge graph data for [google-deepmind/jaxline](https://github.com/google-deepmind/jaxline), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/jaxline
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a2308d62191dbe0768ef3676a45d307a3595be82
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a2308d62191dbe0768ef3676a45d307a3595be82
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d21e15c55d1afb82d23a9824facee2e4b0eeab7.nq.gz
│   ├── 2121dcd4c347a677d56173693c1a795fa2e82571.nq.gz
│   ├── 4179d8fd0f5b76065f2cd2c2dd41c4176ad58731.nq.gz
│   ├── 631944d70ac3e188f69983c2c1b4b7eda683fa9c.nq.gz
│   ├── 666802890a252d4b80acc156149c878e19399872.nq.gz
│   ├── 67402fe76d6ee7010a1ef07606eb0d0855f25894.nq.gz
│   ├── 6f28a03bbd8f5d3708bee6a323f529ef8025715b.nq.gz
│   ├── 73e0b411e0556c6c522c6e655d9727573063f99a.nq.gz
│   ├── 7e3dbe5b53d7c8c467bd6159069d51ea070b2a08.nq.gz
│   ├── 990fd3667b7d5ff298204e7b4003c005450d5468.nq.gz
│   ├── b02fc8e85f7790357acb925242b445f7af261250.nq.gz
│   ├── d6268cc48fb274629634da871a23248d44d2d7f1.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d8403888368616750c3a3966fd6d3c78827ed9fb.nq.gz
│   ├── dd2759457ae8842ed79fde3d48ff537c7a0ceb6d.nq.gz
│   ├── e10f709e16b8c798e9cf5c48d53847b27ba3fb08.nq.gz
│   └── ec524ee3ba239c89dec7a63d429ec579b3ae86ef.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a2308d62191dbe0768ef3676a45d307a3595be82.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[google-deepmind/jaxline](https://github.com/google-deepmind/jaxline)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
