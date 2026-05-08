# Repolex Knowledge Graph of KokaKiwi/rust-hex

RDF knowledge graph data for [KokaKiwi/rust-hex](https://github.com/KokaKiwi/rust-hex), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download KokaKiwi/rust-hex
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b2b4370b5bf021b98ee7adc92233e8de3f2de792
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b2b4370b5bf021b98ee7adc92233e8de3f2de792.nq.gz
│   └── repolex
│       └── b2b4370b5bf021b98ee7adc92233e8de3f2de792
│           └── chunk-001.nq.gz
├── blob
│   ├── 335a15132a2754cda7fd985975fc35be3434a1a4.nq.gz
│   ├── 4132a0436999c2206c0e92aa8929badf12dd5f1f.nq.gz
│   ├── 523dce595ee41e3fd0f954c929c76b86983a9d17.nq.gz
│   ├── 5dfd4b25cc81b75c976faf61a806e4d5091d3067.nq.gz
│   ├── 6435032c64c5b7d220de8ad57d2e8228f6bc1ea5.nq.gz
│   ├── 8c1668611fb1efa5b653ce542c85c65eba94ab77.nq.gz
│   ├── 8f71f43fee3f78649d238238cbde51e6d7055c82.nq.gz
│   ├── a571d3a60209de8aea269eee64066b28e8c99f46.nq.gz
│   ├── a7b461f97c9eb64cd1db0dd060970e485a458c75.nq.gz
│   ├── afa67100666cf48d7b877fbed83fd8722044f211.nq.gz
│   ├── b25d8dd700ea40907c142428bb9b4cf7631fd310.nq.gz
│   ├── c4f4084e37a45b600ad03fb324d7f2b43e9687e2.nq.gz
│   ├── ec48961b9ffeb59158040e364f154dfd15938239.nq.gz
│   └── ff7a3b5c16bd09bcc93724924d9b75a68722aa9c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── b2b4370b5bf021b98ee7adc92233e8de3f2de792.nq.gz
├── filetree
│   └── b2b4370b5bf021b98ee7adc92233e8de3f2de792.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

## Source repository

[KokaKiwi/rust-hex](https://github.com/KokaKiwi/rust-hex)

---
*Parsed on 2026-05-08 by [repolex](https://repolex.ai)*
