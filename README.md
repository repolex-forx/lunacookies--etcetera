# Repolex Knowledge Graph of lunacookies/etcetera

RDF knowledge graph data for [lunacookies/etcetera](https://github.com/lunacookies/etcetera), parsed by [repolex](https://repolex.ai).

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
rlex download lunacookies/etcetera
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 07b3f54999e4f3ff0f027de0144c9349d820ce80
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 07b3f54999e4f3ff0f027de0144c9349d820ce80.nq.gz
│   └── repolex
│       └── 07b3f54999e4f3ff0f027de0144c9349d820ce80
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 26ec50e9bbe2422b5338921e621f6661aa067b1a.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 337d12d177b15357e95bdb1c5b71db21e58f8733.nq.gz
│   ├── 358119cad4c3aa28cf3a1078d44b67f33f180197.nq.gz
│   ├── 80b271d51d2065587671e7888f7cc1ca99ec857c.nq.gz
│   ├── 877deec657d7545c25179c00bbab96ee85c4a4ff.nq.gz
│   ├── 87ca0a622e0ec879a0ae236474e78513fffb6e5e.nq.gz
│   ├── 89f05597148748277357bb0ad945df5418b09195.nq.gz
│   ├── 932a9d88d24c61af70ed3b00375d2ba2b1cf6d1d.nq.gz
│   ├── 96ef6c0b944e24fc22f51f18136cd62ffd5b0b8f.nq.gz
│   ├── a53929bb3897a8074e44c453ab8363a869b44c34.nq.gz
│   ├── ad48841546d75939877ee9793d3ae98875433980.nq.gz
│   ├── c9164b62416ae9433b5e45d4a57896bea571ae30.nq.gz
│   ├── cfe034d568ec12fc6fff831ce3c1fd1dbe55ad9d.nq.gz
│   ├── eaad4bc3e66605c4ea2ccc777c500618e28b0af0.nq.gz
│   └── f07ce900578610b9b191f7e24a4658e14c89d349.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 07b3f54999e4f3ff0f027de0144c9349d820ce80.nq.gz
├── filetree
│   └── 07b3f54999e4f3ff0f027de0144c9349d820ce80.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 27 files
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

[lunacookies/etcetera](https://github.com/lunacookies/etcetera)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
