# Repolex Knowledge Graph of jupyter/notebook_shim

RDF knowledge graph data for [jupyter/notebook_shim](https://github.com/jupyter/notebook_shim), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/notebook_shim
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e1baccba8e2201e41991eb1c6bd96ff94efa10cc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e1baccba8e2201e41991eb1c6bd96ff94efa10cc
│           └── chunk-001.nq.gz
├── blob
│   ├── 06ff90eb4191753a132676a31684374e1faeb691.nq.gz
│   ├── 1e789c3d5ab279ee5b709c13a4581e2860c3771b.nq.gz
│   ├── 1ff24090a0e685e1dc41fc5af1df7b43fb4fb708.nq.gz
│   ├── 354a0468d70855b26a509ec4cc7e4957bcea634a.nq.gz
│   ├── 396330bb9729d2ec595617aef79fb28600d86bd7.nq.gz
│   ├── 3f1a6e55c189552ac6a3c946cfc325ef7d8c2e1c.nq.gz
│   ├── 4b840ac2996fabc307aac6c833c7e9f77201593d.nq.gz
│   ├── 5efd71091d00890010b04945dd997fb5e4939076.nq.gz
│   ├── 60af4c5f16741c7c2fe17cdd9718ae5f6d56d8a4.nq.gz
│   ├── 67e10942982aa709d47cb67ae85f7520d1f6fd02.nq.gz
│   ├── 7fa1a0c8546e63796a271caab5de9541f6bc6e1d.nq.gz
│   ├── 86ea1df7b19e47f993d449e24ce589f2bcac18a6.nq.gz
│   ├── 8ad34552352599c5f0245530de401950323bfe53.nq.gz
│   ├── a87fd8dde31676df0c419bec1eb58361325c0347.nq.gz
│   ├── b258284a0498994bfa6d76721d796f258ffc9501.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   ├── b804bac06e5bd9e07273181b01006f86b960a9f4.nq.gz
│   ├── bebd66c796d0c64948b6e5a779dade87c57c4025.nq.gz
│   ├── c1881060de286b6e65824cf42d336f09ad37ce7e.nq.gz
│   ├── c661b537d4dbfd1e9d80f95e89337de4d58220fe.nq.gz
│   ├── cbcaa80aaff7e511bc252bbee75a48948c0bd2fa.nq.gz
│   ├── d3920b5e37644d75167466bdb04e2dbbc6222263.nq.gz
│   ├── d93de6c12d5ee92aeaf5467fa2afce1eb9c41cc4.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb9e1ae28ef21f9adba3a444920c7a9061533129.nq.gz
│   └── f64737a4d60ee41f3b3ae1cc5174132e8cf86c94.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e1baccba8e2201e41991eb1c6bd96ff94efa10cc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[jupyter/notebook_shim](https://github.com/jupyter/notebook_shim)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
