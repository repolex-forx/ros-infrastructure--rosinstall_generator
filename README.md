# Repolex Knowledge Graph of ros-infrastructure/rosinstall_generator

RDF knowledge graph data for [ros-infrastructure/rosinstall_generator](https://github.com/ros-infrastructure/rosinstall_generator), parsed by [repolex](https://repolex.ai).

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
rlex download ros-infrastructure/rosinstall_generator
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 96b6f03c79c6f178c74694b499442031df9796c5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 96b6f03c79c6f178c74694b499442031df9796c5
│           └── chunk-001.nq.gz
├── blob
│   ├── 2f3644e990879940c6ab0d469f41e99a857bc86d.nq.gz
│   ├── 3681decc64ecb97dbde77aef02a952a45c9e17ba.nq.gz
│   ├── 3cc149302144d4fa1cea512c3b4334fcb65252b1.nq.gz
│   ├── 49037665271423cb72fda7d02cdaa6377dbb1c25.nq.gz
│   ├── 5aa111d21380489d219159e7ab0d3857770de0c1.nq.gz
│   ├── 8be3a199a5f71104efeb23c87800020efe560d47.nq.gz
│   ├── 907137474e2d2f8c628425751c0b1ef4cb14fab3.nq.gz
│   ├── adabbd2de7233a9dcf22a3e7dbe419f9a90d3ea2.nq.gz
│   ├── b7cfad12c5d1c7b28494da9bd49dcc3d55091cd0.nq.gz
│   ├── ba364104e61da04a747c635f64733b6297a7db9f.nq.gz
│   ├── bdcb6355ab0d77cb5824a62a2925217e6ee38cc6.nq.gz
│   ├── d00a4beabfd2d70092a894e757e5711209e54b8d.nq.gz
│   ├── d592f320b262b5080388e2daf32d410cf47ec699.nq.gz
│   ├── e404d4a3761e7c43dc1bc19d1b67f944a970a52b.nq.gz
│   ├── eca60c53802d43c3a357326b094f9c596ddf3e09.nq.gz
│   └── f348c8d624cc09e0501d476e838f399fe41c52ea.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 96b6f03c79c6f178c74694b499442031df9796c5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[ros-infrastructure/rosinstall_generator](https://github.com/ros-infrastructure/rosinstall_generator)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
