# Repolex Knowledge Graph of allenai/molmospaces-resources

RDF knowledge graph data for [allenai/molmospaces-resources](https://github.com/allenai/molmospaces-resources), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/molmospaces-resources
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 55b3c508a5cec4655eee640f0cfa29a8ad3d6078
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 55b3c508a5cec4655eee640f0cfa29a8ad3d6078
│           └── chunk-001.nq.gz
├── blob
│   ├── 001f1c5f9d6ddeaa517ebf348b1278f32f7460dd.nq.gz
│   ├── 10764dfb66201949358e593de9492283410a7c6e.nq.gz
│   ├── 1e199722a79c3257021942484537d0e1f6bbb979.nq.gz
│   ├── 1f9c11e6150e4cde35122b029a33d742eb177450.nq.gz
│   ├── 36ee2b790020bd1b396cd74a3081580e51af27f2.nq.gz
│   ├── 3c8ec63371d4912b1070268a1f7e216b1a26f199.nq.gz
│   ├── 4dd1d2bc4bf895ee0ee3bba2b114c186a1ff2b76.nq.gz
│   ├── 545e499f3bd05ee1701c5196bb50979efed5008a.nq.gz
│   ├── 568a1408a0230eac1c9e6d885f23af26878404c5.nq.gz
│   ├── 5af187ac5eb3da5fbe1f24f19f4a7c8af2cd4319.nq.gz
│   ├── 77d3cdc8165897d71985c0798fb5a5a3793ee721.nq.gz
│   ├── 89ca85e1b57057487610d0b8e2d58acc080607c5.nq.gz
│   ├── 8a717abc3b562341284a7236c365e50449b3faa7.nq.gz
│   ├── 9723c095a2ea9179adeb0697d5c8f6353610da0d.nq.gz
│   ├── aa8ef54e0c305577a2ae7c522235ef32f46e0b7a.nq.gz
│   ├── ca01328ef804770f31b00a846ee1ca037cabc979.nq.gz
│   ├── cd3b9b1918513a3b1834332cca9cd7c5016bd608.nq.gz
│   ├── cdc0db5dcc41fcbc7e7406dee9893d3ee8c5a8dd.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e9f2bff9da620bbbb6d8b5a1caa778e8ad8a5f98.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 55b3c508a5cec4655eee640f0cfa29a8ad3d6078.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[allenai/molmospaces-resources](https://github.com/allenai/molmospaces-resources)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
