# Repolex Knowledge Graph of coleifer/kt

RDF knowledge graph data for [coleifer/kt](https://github.com/coleifer/kt), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/kt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 40b62f46862061f2207ad922413d4e4cd66996ab
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 40b62f46862061f2207ad922413d4e4cd66996ab
│           └── chunk-001.nq.gz
├── blob
│   ├── 070b54c615d3fa588d984c3b9036294d3b72337e.nq.gz
│   ├── 08b71cd9a474a517712d9a9ff9bf4cf4b21bea09.nq.gz
│   ├── 1156dae80463fd710d80ea8604d1ba3887d4d7d6.nq.gz
│   ├── 1f1948d149de8b0fed54b4dfa6b644bf9cc09659.nq.gz
│   ├── 21860269a9958708eaa4e269895db3925b371e82.nq.gz
│   ├── 2ef99f9b4ef65fc74d52a705ddcb7db5cc7453bc.nq.gz
│   ├── 4418f9b38d35b4a4784de94b566b349020d96ad3.nq.gz
│   ├── 51bddeeb2f5274f30a839496cb0df5b7f413c74a.nq.gz
│   ├── 584d98f30a095748902e13fcf87789267bf7fc20.nq.gz
│   ├── 5c8b3d7e3140c03c3d1c53af3a0b713cc648e2e4.nq.gz
│   ├── 618c26fdf83f45c476eaf46eb01aeee0891b991e.nq.gz
│   ├── 63425183d36b0c1345f8376934528a7d59b89251.nq.gz
│   ├── 64c0773eca547fd138b6dc75189479c0469a24a9.nq.gz
│   ├── 697dfa2e975b0103cbedca59395f46e6083bd94a.nq.gz
│   ├── 705ca2709e66ca8cae7ee3d263ad856e25c12c13.nq.gz
│   ├── 709bd25a2f7505414e82fe880076ce6cfdbbe8ba.nq.gz
│   ├── 7252c1adeda7d4730251b5f9687b8d9862bb9cd0.nq.gz
│   ├── 7791800e655b9eeb06d47fcd9f8affcc27fbdf66.nq.gz
│   ├── 78af65936204ed984b328a460c86c498c52256fd.nq.gz
│   ├── 797515c4621ec412fe05e29f43df2ef19debecde.nq.gz
│   ├── 857991eb88c4faca558aca1393f7e0e73eed7bd4.nq.gz
│   ├── 8599ce2b9b25fdd69a8773ff5d0d870caea25874.nq.gz
│   ├── 8d60fe38f5d790a52d18ebd209fe3afd1bfb5336.nq.gz
│   ├── 8f37c55227cacf40722c7a23001ecc643bae466a.nq.gz
│   ├── 9721cde0a6e200e2577a672be96de60838f12694.nq.gz
│   ├── 9f101a4dc1b1d89d219742f40067474027b11e13.nq.gz
│   ├── b051cf5c5683dda6d936a2a82072a613f72075e1.nq.gz
│   ├── b70eba84d23871bd14c0fe43df31e2d3ed6e763d.nq.gz
│   ├── bcd32888ed2c3eab38510370099abad239c7daef.nq.gz
│   ├── cadb42d312e7fb01b196417168afd1278814d18b.nq.gz
│   ├── d85016d12f4393d1b1987b376c86bf401ec2ee61.nq.gz
│   ├── db0249b9607af69c2e285d07deb3a15102bc086e.nq.gz
│   └── e570fbec7d238b9408b4b49d5d3d8db3a96ebcc1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 40b62f46862061f2207ad922413d4e4cd66996ab.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 39 files
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

[coleifer/kt](https://github.com/coleifer/kt)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
