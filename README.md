# Repolex Knowledge Graph of sphinx-contrib/youtube

RDF knowledge graph data for [sphinx-contrib/youtube](https://github.com/sphinx-contrib/youtube), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/youtube
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5238c057730f953ed7c38316aad692a5231294f1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5238c057730f953ed7c38316aad692a5231294f1
│           └── chunk-001.nq.gz
├── blob
│   ├── 003f6753abd0431ba0b69a8a7c0bdfa232683bdf.nq.gz
│   ├── 066676bc740103e92db82f9b45e449f250725c4f.nq.gz
│   ├── 08cc9123bcb680b17848564d4585c7298ee44186.nq.gz
│   ├── 0f2f5cdda8ea555889bd6ebaeb40ae56748927dd.nq.gz
│   ├── 1934f553b3666b425cde9d362738e33d3ca716ff.nq.gz
│   ├── 215064d62902efa7416e0f47b95b14f53d0fec09.nq.gz
│   ├── 2637d2f5de31c962548d359f679406e56076054b.nq.gz
│   ├── 2762c058785897ff768717ea597a2d19a06927a5.nq.gz
│   ├── 27de286b41871827b8b17ed8bc7515d131863225.nq.gz
│   ├── 398381b03c090e2add1a4945ed1ad0e8130a74b8.nq.gz
│   ├── 52fc4ecc5ed16e766d09594f9f5ce64971b2277d.nq.gz
│   ├── 5be4a95977d56586d353ae8f5d9e3cd69866b6a3.nq.gz
│   ├── 5c06d73137c2661f39eaf0a902df93624a4b7b29.nq.gz
│   ├── 6777a31eda80cb845a7bff383c4050fe535d68ff.nq.gz
│   ├── 690201636df8d659b6ce68fc0d340e5fbc2410a1.nq.gz
│   ├── 6c3a28492c2265fea9317f304013415acab3a694.nq.gz
│   ├── 779bea254a0b6b39ca559e1f5b829ab0778b36d2.nq.gz
│   ├── 90e16ec51d2defa8b51a1fa8b9a1e93d4d9e1689.nq.gz
│   ├── a2017045c5ff985dc375bc7a83bb55017bc67ebe.nq.gz
│   ├── a59acfd1f2e602d9d5b15326b7ca1f6ce59b46b6.nq.gz
│   ├── a6cbec3e036a5f04c0fc3168ecf9774bec8486be.nq.gz
│   ├── a991ef5dc4ebb181961036901da36280b4c760fc.nq.gz
│   ├── db703e2c596014231db58bae85dc79972e9518e6.nq.gz
│   ├── e0ba3ae00b1ebbc277e4ac95d735097f90fa058a.nq.gz
│   ├── e1509f6619567158fae9f079db5d942f045026d9.nq.gz
│   ├── e684bfa24750c15ce5a7266a02706b46a2bbe3da.nq.gz
│   ├── eba7646a587bca5e2b7923eaa90c8fad042ebd91.nq.gz
│   ├── fbb4604cc031af7af21af76183f199053abba5c6.nq.gz
│   └── fd708cf3d892294c01ddcad9bec3fb9cee4abff9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5238c057730f953ed7c38316aad692a5231294f1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
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

[sphinx-contrib/youtube](https://github.com/sphinx-contrib/youtube)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
