# Repolex Knowledge Graph of tox-dev/tox-docker

RDF knowledge graph data for [tox-dev/tox-docker](https://github.com/tox-dev/tox-docker), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-docker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ccadc6e341edefdf57122318d75906acaf4c25bf
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ccadc6e341edefdf57122318d75906acaf4c25bf
│           └── chunk-001.nq.gz
├── blob
│   ├── 002b38c0266b2f8750d46456f8b71cff8d82d109.nq.gz
│   ├── 1828152d986973d92dac9c76cff2de2fc3da990f.nq.gz
│   ├── 1ac4670916951037b3caa0e8afd59dc28bf5fe2e.nq.gz
│   ├── 255e2b8216c84fe7b4ed3cc19df0d6bb200f677c.nq.gz
│   ├── 28abf448504a705592667e20ea1243753552ec3d.nq.gz
│   ├── 3c09427f913c8cb55b0949dcda255b61f9663b3d.nq.gz
│   ├── 3d618ff5bd0d075ec1fbd8821bfc00fc60f58dd3.nq.gz
│   ├── 452abf8bb18fa9568ff6d0e5c9214e02ffd948e2.nq.gz
│   ├── 4f1afa38037c7d426466f65380def74a09ab87b6.nq.gz
│   ├── 5bd8bb2a91455ed503fb3a347eb6e9547c06e0c7.nq.gz
│   ├── 5e43652cc72633c08e808826e62f526c18b395e3.nq.gz
│   ├── 635d810f0ff335ddaeb27ae31837967f41eb3d3d.nq.gz
│   ├── 6ec0118b298d7ac02ea1670f44c4f55b9eecfacd.nq.gz
│   ├── 6ff3ac592ab697a0617d89a3d24cf39052ae3a9f.nq.gz
│   ├── 70dff18772fe004374e7ef5685dcf269e7336dc6.nq.gz
│   ├── 7305cf89f646ac1cfa8d970715b0a1f0f2655e1b.nq.gz
│   ├── 733a24fa7ae1514639061e4ad4d43fe78358e597.nq.gz
│   ├── 7422b593c67fa76b4872d36027554ff64727e9ae.nq.gz
│   ├── 7da2c6e85dae8779a484a4b72f8e34d10f39b9ac.nq.gz
│   ├── 80cbf7ca19badb891856300f5d00f19e9254c155.nq.gz
│   ├── 8842f276413124721dc936f282e784e35ccba1c4.nq.gz
│   ├── 898ea6e9d69c20b52f05d89423e161ce95d7dc23.nq.gz
│   ├── 94035e0e6d23bbfb7814c3498c3e3f7edb59d771.nq.gz
│   ├── a34cf64b96a897a4eef0046c860e3a089fd6ce4e.nq.gz
│   ├── a6210d3d8a7988fdee6556eeba665d6b58ee6db4.nq.gz
│   ├── a9d04211686759d4b895519353c519fc4d7a0f72.nq.gz
│   ├── ac60b1ebf55633be8d1fcdc3cfa49696f107f152.nq.gz
│   ├── b6e38c4c87d24cde5516c9844d6275607776b329.nq.gz
│   ├── c5d4fff93384a7b4f91ff88b98ec480412a4e7d8.nq.gz
│   ├── cf96c012dc839af05a7b70b833d469fe5992d43e.nq.gz
│   ├── db56d87c2f6fe604ceff6d42e8367fcf4c4efe7b.nq.gz
│   ├── db5d795c9fe6beba0e37aed0a3b9bbb41bacafe2.nq.gz
│   ├── e3f9bf8c591e0cd7cb114b928200e0c051c33f92.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ebd8490f04cc1a3ec04735e9bcbe91b08d8a2a94.nq.gz
│   ├── ed2979cccbc8bfd2026adcc35c61e134f0f86ba5.nq.gz
│   ├── fdc5ce18eafb973cb0503b6f01fc2bd8756fd660.nq.gz
│   └── ff30e7bb4b6205df6581de3d6669a0e0623cd476.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ccadc6e341edefdf57122318d75906acaf4c25bf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[tox-dev/tox-docker](https://github.com/tox-dev/tox-docker)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
