# Repolex Knowledge Graph of serde-rs/test

RDF knowledge graph data for [serde-rs/test](https://github.com/serde-rs/test), parsed by [repolex](https://repolex.ai).

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
rlex download serde-rs/test
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bbb18e2db032ec5da07e07368e4d55647cf10229
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── bbb18e2db032ec5da07e07368e4d55647cf10229.nq.gz
│   └── repolex
│       └── bbb18e2db032ec5da07e07368e4d55647cf10229
│           └── chunk-001.nq.gz
├── blob
│   ├── 03b3b7b76168766962f6e5d545b6675428603e47.nq.gz
│   ├── 1630954f4695a89e1d5fde6ecdfe907887a750a3.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 1ff4c73010a47f96989f6f0803319a0146c8ca41.nq.gz
│   ├── 245bbe8b9a1090e073b0236be1d2cf18da37a87d.nq.gz
│   ├── 24e3c08d0bd45b09e5ff00408ae91d084538ae43.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 4fffb2f89cbd8f2169ce9914bd16bd43785bb368.nq.gz
│   ├── 73a7e45c38b953793ae35b32f93b63a1563d2379.nq.gz
│   ├── a5d9e1da4b0dd4c40784621f796d2217bd4f39f0.nq.gz
│   ├── dc54d4d10e74bd9b85f449a2eb259e4bd3f18d03.nq.gz
│   ├── e6321d7237e9d176d9e334f2424cae1bbc3ea76f.nq.gz
│   └── e935799f630a792f0eef110e2a0cc0e7ac6f9cf4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── bbb18e2db032ec5da07e07368e4d55647cf10229.nq.gz
├── filetree
│   └── bbb18e2db032ec5da07e07368e4d55647cf10229.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[serde-rs/test](https://github.com/serde-rs/test)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
