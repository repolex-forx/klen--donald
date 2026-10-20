# Repolex Knowledge Graph of klen/donald

RDF knowledge graph data for [klen/donald](https://github.com/klen/donald), parsed by [repolex](https://repolex.ai).

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
rlex download klen/donald
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d48bf0f0f91a758cfb0498e83fda6d5aff4ecb91
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d48bf0f0f91a758cfb0498e83fda6d5aff4ecb91
│           └── chunk-001.nq.gz
├── blob
│   ├── 01f42e766492c1ffc3ff4edba6c4468c800e25cd.nq.gz
│   ├── 164a5b0c1cf00508586efdc9c714eacdd0b9f489.nq.gz
│   ├── 19bf0c2b9f60a79ab2949f7498bd16284c3bacbb.nq.gz
│   ├── 27a6c88a783c28f23c29c82c74941ba64d4e18c5.nq.gz
│   ├── 299ad396898da9fa98daa2c3799d819ae52149bf.nq.gz
│   ├── 2abfc004da82c6488afbe8d6498dec00aa91ec1a.nq.gz
│   ├── 32fd92c7707de3c6b8e0a9243f6dddc754855e03.nq.gz
│   ├── 47e75c5dd4b34155c6dc5581206038dc8e515861.nq.gz
│   ├── 4a060cc8ce501e4a5b9157c2f5ed52285582dd60.nq.gz
│   ├── 5463df9ebda46573609c9bac17b257cf073f5865.nq.gz
│   ├── 5907cfc43422fb1ee878df49fb7570f91046457a.nq.gz
│   ├── 5a50b91f138590bc5e5977bff67db89b7c7421e4.nq.gz
│   ├── 5c9935bf610b6afd6093eef0e0a9654842b04912.nq.gz
│   ├── 5e185f98f03e2711e66325630faf5b54d7b6d213.nq.gz
│   ├── 6c761af246ffcb47be3165dd63ab84f92a7a86c3.nq.gz
│   ├── 70f322e0e6e00ef63737ebeeb086fe92681fe882.nq.gz
│   ├── 7d6c961924ecd45b7996e0c7fa3cf32c7e5d4158.nq.gz
│   ├── 84914d67667d2238b16bc5cd18527d0723745d2e.nq.gz
│   ├── 8b137891791fe96927ad78e64b0aad7bded08bdc.nq.gz
│   ├── 8c4312abc4dacf29dd630abaaa2e92a70a3d368c.nq.gz
│   ├── 8f877c5a7571273e3190d757029d3c63fa6fd620.nq.gz
│   ├── 9750fc3fc58344b763cea2294b02827ad68e3d93.nq.gz
│   ├── a79b47ea6ea9f64ee3f36a4623db5d36a1138f86.nq.gz
│   ├── c075ed3a47815a8afb4a048270de14037427c11b.nq.gz
│   ├── c5f85bef4bfa45ad95ea0cc0861eda46ad179f4e.nq.gz
│   ├── c66568429089a69863f57cf72bbc47ac25231227.nq.gz
│   ├── cb778568c01d84831d5759d4af8821336daf18f5.nq.gz
│   ├── cf5ae2352a555062d1b09acaf8ee16e9dafb5c47.nq.gz
│   ├── d2eb829a0b6a05fab4ab5b3b85cd0ffc1563b31f.nq.gz
│   ├── d3750485411d6b70554e443181787c352a1b7904.nq.gz
│   ├── e0dbad1b59780ee5de2d999eb45fd21b81226802.nq.gz
│   ├── e1eea2029906cb1c9affbd0268d8bffdcfa94a8c.nq.gz
│   └── ea2eb1859f21fc648bd2770f764e83a437a76da9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d48bf0f0f91a758cfb0498e83fda6d5aff4ecb91.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 40 files
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

[klen/donald](https://github.com/klen/donald)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
