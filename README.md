# Repolex Knowledge Graph of agronholm/asks

RDF knowledge graph data for [agronholm/asks](https://github.com/agronholm/asks), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/asks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e3f2b097fad33c0063e3461385ceccfdeb8bfd32
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e3f2b097fad33c0063e3461385ceccfdeb8bfd32
│           └── chunk-001.nq.gz
├── blob
│   ├── 00c77e1f55781aebe90a1aa155a52b59f71f2fa3.nq.gz
│   ├── 01778ae797c67dde297ae6df41da17d01fab29ac.nq.gz
│   ├── 076eecb696f1e6e0c0ba296bfa0f16334184c94e.nq.gz
│   ├── 0f0881fc4ab38aeba3045fc54925696d1f63d9e4.nq.gz
│   ├── 0f1c989097d858bc1c3d69bc1e294dbb48d102e7.nq.gz
│   ├── 1ae48b038768ea012d548b3b751969bf35c8f476.nq.gz
│   ├── 24dd42c514d6509a2478b2474b0033da9afbb143.nq.gz
│   ├── 2df809e1c78bf3d26a34e114492285609386d2a0.nq.gz
│   ├── 2e7713827ef3b0edbeb5dc3ce493dfeaf9dba113.nq.gz
│   ├── 3010d91d82eb0081eb30ea40bc8fca5222ff6771.nq.gz
│   ├── 3573badf6a7afede64dd8729a031f861c27ff8ff.nq.gz
│   ├── 35cf20b7faacf44af5baa766cfda172b77c43d51.nq.gz
│   ├── 466725558b7c1c8b207c5bb82a6a8124e601dbec.nq.gz
│   ├── 55ea92c63c255ce6642d4ad52b6dbd13522a5dd7.nq.gz
│   ├── 57e49d7777e636024280c363b567ff69e0657bbe.nq.gz
│   ├── 5dd5323906517ab0bcc127590cffb8adde2a16da.nq.gz
│   ├── 60c6fe21a0e0e954c7fd364a9ef8261309542da3.nq.gz
│   ├── 63b2a998263ede7efc123b1896b94f731027543f.nq.gz
│   ├── 86a7ec165eb85c272f2371f588edcd1e13828e01.nq.gz
│   ├── 86b904882728672cc6e60d3596feb7faa864b704.nq.gz
│   ├── 8a19cb54ca09d7c522bf40d0221a10da3a6c46f8.nq.gz
│   ├── 9f7fbe81a25737806ac1db721fca2e1fcc2db604.nq.gz
│   ├── b9bfd32e500bc8091b7890dfcd31cc59f387f9e4.nq.gz
│   ├── bbd6446efacb25e10735a7da72eebbe37449fdd6.nq.gz
│   ├── c32575c861760b499d2fe956023641ea59f1447c.nq.gz
│   ├── dcd29aca193b6e9ac12f91414d27c3fa178065fa.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb0478c3a629e9b2b2d853216be85066b1963dbb.nq.gz
│   ├── ebb8a0eb04bbcab3528dbccd964e6e6dba08a95f.nq.gz
│   ├── f3e38151b5e6ea2560b30b0247d4dbc9e2545393.nq.gz
│   └── fbd8bd17bd1302201bb311e006a1e2de1330aa27.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e3f2b097fad33c0063e3461385ceccfdeb8bfd32.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 38 files
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

[agronholm/asks](https://github.com/agronholm/asks)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
