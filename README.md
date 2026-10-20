# Repolex Knowledge Graph of asottile/classify-imports

RDF knowledge graph data for [asottile/classify-imports](https://github.com/asottile/classify-imports), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/classify-imports
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e63b6c6e66ba4745c05331c3d21e513bf30132f6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e63b6c6e66ba4745c05331c3d21e513bf30132f6
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c5a37eb0adeb312718e533d0a4fbcbea6880056.nq.gz
│   ├── 203bfbc3224dd4f68715ac95609b79f80ad964ca.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 3fdffa121e3b0e62264cdf10bc360c93537670b7.nq.gz
│   ├── 5370c9485451439199ab7ab9ba30c95d9a046275.nq.gz
│   ├── 9f9f85d82a399047323bcb4b3ef825874c0b9bc4.nq.gz
│   ├── a15a8d1a4edb8c68a20a8a1488529cd69b42f385.nq.gz
│   ├── b13c15d0ae85284f3d41360fe0ba4db78f2ecc4d.nq.gz
│   ├── c21295979e414f15c29117b51c8c2eef778f4913.nq.gz
│   ├── cf4350e288bcb286188c09ebb3414224a82935fd.nq.gz
│   ├── d86d9ea06347dbd79c04079484155ea94fa2c3ed.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e63b6c6e66ba4745c05331c3d21e513bf30132f6.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[asottile/classify-imports](https://github.com/asottile/classify-imports)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
