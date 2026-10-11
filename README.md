# Repolex Knowledge Graph of pytest-dev/pytest-bpdb

RDF knowledge graph data for [pytest-dev/pytest-bpdb](https://github.com/pytest-dev/pytest-bpdb), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/pytest-bpdb
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c6a97b8d8bc750dd13b1864ef911facecb300daa
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c6a97b8d8bc750dd13b1864ef911facecb300daa
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ace0dfd43912adb7310fc61f35c33919037ab6d.nq.gz
│   ├── 1ec6cd107ede709e849f0b0f96107c70e25c6c47.nq.gz
│   ├── 238fcdc745104174dd72c743d1c71392c5b8f357.nq.gz
│   ├── 278521ec57adb84ea51a7c5c77629862246b6401.nq.gz
│   ├── 310fa80138f43a17e5c977c993c6c337caf180bc.nq.gz
│   ├── 5e4090017a9bec5de60a745d17007a9e95f31a43.nq.gz
│   ├── 6ae413ab9ca82b738b08344ce7209dac79effbfb.nq.gz
│   ├── 74e8560c42891fbc24688230c3f217c2a77eaea3.nq.gz
│   ├── 773d1c2c104d9f8bcc8b9e6d933fe34f9d8858a4.nq.gz
│   ├── 7955f68dd48c3212d71a8c0a7d7678f77a8ea52a.nq.gz
│   ├── 7e426dc6d7b44ebbf533d18df026a8ad14803d51.nq.gz
│   ├── 84388812acae746ec19dcfa4d372e13fe72160dd.nq.gz
│   └── e6448a7eee06ab743ebd64d5d9f2b1b8817e0fe2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c6a97b8d8bc750dd13b1864ef911facecb300daa.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 19 files
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

[pytest-dev/pytest-bpdb](https://github.com/pytest-dev/pytest-bpdb)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
