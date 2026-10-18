# Repolex Knowledge Graph of explosion/srsly

RDF knowledge graph data for [explosion/srsly](https://github.com/explosion/srsly), parsed by [repolex](https://repolex.ai).

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
rlex download explosion/srsly
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 050951efad45e2347f2b90b52398affcecf86fca
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 050951efad45e2347f2b90b52398affcecf86fca
│           └── chunk-001.nq.gz
├── blob
│   ├── 05b92b63d7e4138a91b743550fe9d04db592ec96.nq.gz
│   ├── 0c94d82bbd75a2607d9851850eb4457133cf640d.nq.gz
│   ├── 101d3f5282ea1572cee41e16ccf92dcfb890bd71.nq.gz
│   ├── 13d0f66096422d870e52b0bfd6775c4ab4157c23.nq.gz
│   ├── 1d01e5496545d0ad9a7a1ee884edd218e8d79e28.nq.gz
│   ├── 33355d0846642ef971c293f4c3726a5ad399c7ea.nq.gz
│   ├── 3a2df966d82d73e78cc437c09ae46a9abcfac5a7.nq.gz
│   ├── 43460125ec8d0b274ffac39b50b5d81df0642ba8.nq.gz
│   ├── 525938021c5a28c1baa17a46db4843615f9266fe.nq.gz
│   ├── 528787cfc8ad81ed41822a8104b60b4896632906.nq.gz
│   ├── 56a691da92dceb286543e3f7ace1a49f1c99004e.nq.gz
│   ├── 7d296aa078faa13fb5d70305709b4a2b41e67bb0.nq.gz
│   ├── 8097293b3c364c91c1b9a217a1f683a991c0b3f2.nq.gz
│   ├── 85f0164098fc80d408ab03c302b6aa6c3dadc62c.nq.gz
│   ├── 9a86d29b5e9bca1ef2845dae211a098fa26fa79f.nq.gz
│   ├── 9dcc358968cd1e80b2dc43670423ee8b36bdfe3f.nq.gz
│   ├── a3a842cb1a4498fe3071064373d3ca1c1e26aef1.nq.gz
│   ├── af888ffdf8da3bd7b8d895d7de4e38ef825cb22c.nq.gz
│   ├── b0b222fc69bd6e6e1a171f4e02a7de1837c5347a.nq.gz
│   ├── b5cbd431d7555fe959bfca544872adfeb01e4423.nq.gz
│   ├── c31bff0196c6ebc8e948fd0a5536a82acb7f9b50.nq.gz
│   ├── c43120c96182895496403bbaac1caae3d4f12eb5.nq.gz
│   ├── e208c3a5ba5a9b48730f34d384a4f498316c1c01.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e755217d8049aae68645cb7ab135e21a70350900.nq.gz
│   ├── f13654f124242919072f38b6186fcaad40164e79.nq.gz
│   └── fed528d4a7a148fd0bf0b0198a6461f8c91b87e9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 050951efad45e2347f2b90b52398affcecf86fca.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[explosion/srsly](https://github.com/explosion/srsly)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
