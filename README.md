# Repolex Knowledge Graph of ipython/comm

RDF knowledge graph data for [ipython/comm](https://github.com/ipython/comm), parsed by [repolex](https://repolex.ai).

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
rlex download ipython/comm
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ba1c862a4cdb28d2aebc9b77c3b9616dbcffc44c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ba1c862a4cdb28d2aebc9b77c3b9616dbcffc44c
│           └── chunk-001.nq.gz
├── blob
│   ├── 396330bb9729d2ec595617aef79fb28600d86bd7.nq.gz
│   ├── 3b9c7da31d0db88f6acbe12011e02e345a0011d6.nq.gz
│   ├── 51ba9eecb5ba67232a4a6b1d67a0c9b687771ca1.nq.gz
│   ├── 6ce004e57818f464e4286a699901dcc4b3053cdc.nq.gz
│   ├── 6dcaa1311004dc172defa1e32d02dd836f8e7641.nq.gz
│   ├── 92aa6d814e8e86cfde3f7170ae7df732761648d6.nq.gz
│   ├── 992b1c2e324d0a82de656aef39ae4aa9750c3ac4.nq.gz
│   ├── ad8bf66a0ddaa07152c04b0b5abf6d2930ea06bc.nq.gz
│   ├── b8a9f86f129180ddfe8abb32261bdac2f68ab6ca.nq.gz
│   ├── c576a54877c836891c83f5d6d0e1e817581d22c6.nq.gz
│   ├── d5f757f0ea880390f5eeb9ee6c4b8b99573395bf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eee1b58d9ed05bdf064d2550c708a6015285de67.nq.gz
│   ├── f345f602adc5bba108346ed134441317e29a5127.nq.gz
│   ├── f6743a9bf2cdf500e843de3e1f6b3077d172161f.nq.gz
│   ├── fcdd3e88b66ec9b10362685146ef2a36088e54f3.nq.gz
│   └── fe0ad248a8a0040683d0ea7a28f59e0b51cd1ea2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ba1c862a4cdb28d2aebc9b77c3b9616dbcffc44c.nq.gz
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

[ipython/comm](https://github.com/ipython/comm)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
