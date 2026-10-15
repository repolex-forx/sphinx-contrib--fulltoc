# Repolex Knowledge Graph of sphinx-contrib/fulltoc

RDF knowledge graph data for [sphinx-contrib/fulltoc](https://github.com/sphinx-contrib/fulltoc), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/fulltoc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8c09d8225e98cf8543d60c60b6c36e4b7b8b1d56
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8c09d8225e98cf8543d60c60b6c36e4b7b8b1d56
│           └── chunk-001.nq.gz
├── blob
│   ├── 0eee2117c8942cd5078ed7e479f7ffbc776bdd76.nq.gz
│   ├── 2279e73a278b45adb5dbcffaf3ce526c554aac23.nq.gz
│   ├── 28ea03b0b3a5b318ec6f51d347d4b815bf28ac69.nq.gz
│   ├── 62f38a592fd93d6b97aa333be397d4702b7a0bf4.nq.gz
│   ├── 68043732505ce6a7a6b4076ee3448631e3857754.nq.gz
│   ├── 79290327b69362306924790cc91ecde1c9a87848.nq.gz
│   ├── 9612f4791228cb71c1f4fbb0a6a14d4485a53a70.nq.gz
│   ├── 9e81316d1b172e65af4af5d9fc1c0e58b98cbf99.nq.gz
│   ├── a5021c60e36ae085d1ef96c1fed9d88c2f65dd53.nq.gz
│   ├── b37cee243328dbaea5300e3036482a5b57b350a2.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── cbd95cb21826cd00424f0467debf1685ea72fe2b.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── e49307a0c796a893b945860eeb0409790fcc5196.nq.gz
│   ├── ebbe8385de906ff07f8257655cae94e3ddb9f4fa.nq.gz
│   └── fac1d2b783514542cea61531146a2868bba7d270.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8c09d8225e98cf8543d60c60b6c36e4b7b8b1d56.nq.gz
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

[sphinx-contrib/fulltoc](https://github.com/sphinx-contrib/fulltoc)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
