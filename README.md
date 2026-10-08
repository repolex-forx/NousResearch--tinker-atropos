# Repolex Knowledge Graph of NousResearch/tinker-atropos

RDF knowledge graph data for [NousResearch/tinker-atropos](https://github.com/NousResearch/tinker-atropos), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/tinker-atropos
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ac3a1650e33ab5bfeee2df32f511120a259d667f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── ac3a1650e33ab5bfeee2df32f511120a259d667f.nq.gz
│   └── repolex
│       └── ac3a1650e33ab5bfeee2df32f511120a259d667f
│           └── chunk-001.nq.gz
├── blob
│   ├── 058c9f2dbaa20e3e0a23d888665ca30ee147b79c.nq.gz
│   ├── 0923724030940eaf8af2ef375ccbd41afb959f02.nq.gz
│   ├── 1f0aa2f943b14571ccb60b246b72f985bc499240.nq.gz
│   ├── 29863adf816489653fe8b29e2d699afe8f7f6c86.nq.gz
│   ├── 3ac09ceb27dab4aaf9801e35ebd86248a158b91b.nq.gz
│   ├── 3d6550b2e4defbc9e3cf20fee1c7b18e5d18deda.nq.gz
│   ├── 55b24f61322428b21f28d86f25b3478e8b9e0224.nq.gz
│   ├── 5cf5c172980d7072122c2a4580f6e42e3aa27427.nq.gz
│   ├── 67593041aeaf92993e8d9bb53e98d845e6ba2dec.nq.gz
│   ├── 6e1aaa522f66a39fae3e6ff9deac4f585255c221.nq.gz
│   ├── 8c1acbf04eea29ff077a491332f5114c2cca6085.nq.gz
│   ├── a8c5c5f7176a3e2bbda6a1d46ab3675416050501.nq.gz
│   ├── bf5b2eda7201c41e317ca306d00c9ede6eb47a7e.nq.gz
│   ├── cf5c34992ca094caa08c9c101509c39e450cd107.nq.gz
│   ├── d830eeb89b190a2683d4e58165a3998000368793.nq.gz
│   ├── dd273931d70ca89d121996044a9c827e1cc58f93.nq.gz
│   ├── df084841356a5891342d7c22f2d3048b46450ce6.nq.gz
│   ├── dfeb938f69ea9ececbb738f3aa1d551cdce001ea.nq.gz
│   ├── e51527d0dfbb3cb7be9082297fe64520283721d9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ef428f71ab277df16f9657c035366b7e450b4cb9.nq.gz
│   ├── ef493e288408b1d356e91a8c2e1df18c236b3091.nq.gz
│   ├── fdb1c4c2975f1f98be2895bb680ebbb3821b4b21.nq.gz
│   └── fe4970eadacbd6bb1de4981b53caf904c72c36d4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── ac3a1650e33ab5bfeee2df32f511120a259d667f.nq.gz
├── filetree
│   └── ac3a1650e33ab5bfeee2df32f511120a259d667f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 34 files
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

[NousResearch/tinker-atropos](https://github.com/NousResearch/tinker-atropos)

---
*Parsed on 2026-10-08 by [repolex](https://repolex.ai)*
