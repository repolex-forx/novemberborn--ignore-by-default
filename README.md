# Repolex Knowledge Graph of novemberborn/ignore-by-default

RDF knowledge graph data for [novemberborn/ignore-by-default](https://github.com/novemberborn/ignore-by-default), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download novemberborn/ignore-by-default
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c2fefc478188edca24a2e3fb2a7bda9f558fbe2f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c2fefc478188edca24a2e3fb2a7bda9f558fbe2f.nq.gz
│   └── repolex
│       └── c2fefc478188edca24a2e3fb2a7bda9f558fbe2f
│           └── chunk-001.nq.gz
├── blob
│   ├── 07edda07e7218b5781b99c3dbbf69d28643d31f8.nq.gz
│   ├── 1aea20b5654ae59d3614a16acd214e593930b85a.nq.gz
│   ├── 3c3629e647f5ddf82548912e337bea9826b434af.nq.gz
│   ├── 43c97e719a5a824700932f72e6e7e6748ce45d01.nq.gz
│   ├── 90a908d2e871cbe756be0a99618e910fb36ba268.nq.gz
│   ├── ac3ba060e654ca3de5267d6edf5d2c409a81808a.nq.gz
│   ├── e47e0501c603eb22a97011201acfba09f53e416f.nq.gz
│   ├── ee1e367897fb23db63bccadd30f413c1eb957634.nq.gz
│   └── f9281a9a128746a2610ba94a4608e69f72c21f4d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── c2fefc478188edca24a2e3fb2a7bda9f558fbe2f.nq.gz
├── filetree
│   └── c2fefc478188edca24a2e3fb2a7bda9f558fbe2f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 18 files
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

## Source repository

[novemberborn/ignore-by-default](https://github.com/novemberborn/ignore-by-default)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
